---
id: 8yr53nbv79ezaxb7vj4gpv4
title: Log
desc: ''
updated: 1731882027685
created: 1731696290865
---


## t.2024.11.15.10

- static
  - removed .well-known with its atproto-did
  - replaced
    - avatar.jpg (and updated _data.yaml "image")
    - logo.png
    - favicon.svg
- updated README.md
- deleted CONTRIBUTING.md
- _data.yaml
  - changed image, icon,  

## t.2024.11.15.11

- removed "// For testing purpose of CSP middleware" code in main.js

## t.2024.11.15.12

- moved everything into a "src/site" folder
- renamed docs to pages (so as not to confuse with the github pages-mandates top-level docs)
- moved README.md, netlify.toml back out to top-level

## t.2024.11.17.01

- played with google fonts, for some reason have to delete all the alternates from from variables.css

## t.2024.11.17.14

- removed from _confit.ts, shouldn't be needed but it's a great feature

site.data("scheme", async (mod: string) => {
  try {
    const url = `https://deno.land/x/lume@v2.4.2/${mod}`;
    const { defaults } = await import(url);
    const { Options } = await analyze(url, { maxDepth: 2, private: false });

    mergeDefaults(Options, defaults);
    return Options.children;
  } catch (error) {
    console.log(`Error generating the documentation for ${mod}`);
    console.log(error);
    return [];
  }