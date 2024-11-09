---
id: k20qg2pdevcde1te7i3y2al
title: Log
desc: ''
updated: 1730847113179
created: 1730847056679
---

## t.2024.11.05.14

### npx gluegun new sf-cli --typescript

__tests__/cli-integration.test.ts 103ms
.eslintrc.js 21ms
package-lock.json 90ms
package.json 15ms
src/cli.ts 6ms
src/commands/generate.ts 5ms
src/commands/sf-cli.ts 16ms
src/extensions/cli-extension.ts 3ms
src/types.ts 2ms
tsconfig.json 2ms

Generated sf-cli CLI with Gluegun 5.2.0.
Using TypeScript

Next:
  $ cd sf-cli
  $ npm test
  $ npm link
  $ sf-cli

Since you generated a TypeScript project, we've included a build script.
When you link and run the project, it will use ts-node locally to test.
However, you can test the generated JavaScript locally like this:

  $ npm build
  $ sf-cli --compiled-build

