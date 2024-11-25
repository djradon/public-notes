---
id: iw4bi3tr6dgns0m5932h2nc
title: 2024 11 20 Getting Things Workabl
desc: ''
updated: 1732162845231
created: 1732137048127
---

## dev mode (dave)

I'm want to add functionality so that I can work on the _combined files manually for dev purposes. A couple of thoughts:

a global tidyBeforeBuild option: if false, don't tidy first

But that still wouldn't prevent copying. Which ultimately you might want to control "per-inclusion", but for now maybe we'll just start with a global suppressInclusionCopying option. We might want move this from prepareInclusions back into multisource.ts:

      // Copy included paths into the combined directory
      await copyIncludedPaths(localRepoPath, combinedDir, options);

Don't change any code yet, just let me know what you think.


## dev mode (chatgpt)

Your proposal to add `tidyBeforeBuild` and `suppressInclusionCopying` as global options makes sense and aligns with making the system more flexible for development purposes. Here’s a breakdown of the thoughts and potential implications:

---

### Global `tidyBeforeBuild` Option

- **Purpose**: Controls whether the `_combined` directory is cleaned before the build starts.
- **Use Case**: 
  - For development, you might want to retain changes made manually to `_combined`.
  - For production, this ensures a clean slate before copying files.
- **Default Behavior**: 
  - It makes sense to default this to `true` for production-like behavior.

**Implications**:
- If `tidyBeforeBuild` is `false`, you should skip `tidyCombinedDir` entirely, ensuring the manual edits in `_combined` remain intact.
- Logging should indicate whether tidying is skipped for better clarity during debugging.

---

### Global `suppressInclusionCopying` Option

- **Purpose**: Prevents the copying of files from the source repository to `_combined`.
- **Use Case**:
  - For development, you might want to use `_combined` as a working directory without overwriting files.
  - Could later evolve into a per-inclusion option for more granular control.
- **Default Behavior**:
  - Default this to `false`, as copying is expected in most cases.

**Implications**:
- If `suppressInclusionCopying` is `true`, you can skip the call to `copyIncludedPaths`.
- Moves the copying logic from `prepareInclusions` to `multisource`:
  - `prepareInclusions` remains focused on initializing or updating repositories.
  - `multisource` orchestrates tidying and copying, making it easier to control suppression globally.

---

### Moving `copyIncludedPaths` Back to `multisource`

This move makes sense because:
- **Centralized Control**: 
  - `multisource` already handles global options like tidying.
  - Adding suppression options fits naturally in this layer.
- **Separation of Concerns**: 
  - `prepareInclusions` is responsible for repository setup, not content copying.
  - Copying behavior aligns more with the overall orchestration layer.

---

### Proposed Flow with Options

```plaintext
1. If `tidyBeforeBuild` is true:
   - Tidy `_combined`.
   - Preserve `_src-repos` if needed.
2. For each inclusion:
   - If `suppressInclusionCopying` is false:
     - Copy the included paths into `_combined`.
3. Repository preparation (always):
   - Initialize or update repositories with `prepareInclusions`.
```

---

### Future Per-Inclusion Suppression

Introducing a per-inclusion option for copying is a logical next step:
- **Example**:
  ```typescript
  inclusions: [
    {
      url: "https://github.com/example/repo.git",
      options: { suppressCopying: true },
    },
  ];
  ```
- **Granularity**:
  - Developers could selectively suppress copying for specific repositories.
  - Allows flexibility for working on only certain parts of `_combined`.

---

### Recommendations

1. **Implement `tidyBeforeBuild` and `suppressInclusionCopying` as global options**.
2. **Move copying logic back to `multisource`**.
3. **Log the behavior for both options**:
   - Indicate whether `_combined` is tidied.
   - Indicate whether copying is skipped.
4. **Plan for Per-Inclusion Copying Control**:
   - This can be added later once the global options are tested and stable.

---

Would you like assistance implementing or refining this plan further?

