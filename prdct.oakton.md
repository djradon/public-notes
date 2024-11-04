---
id: bvqecybtit80as0koga8eth
title: Oakton
desc: ''
updated: 1730495671673
created: 1708903572290
---

- [[c.Software.CLI-framework]]
- url: https://jasperfx.github.io/oakton/
- written-in: C#

## Description

- Easily enable tools to expose multiple commands

## Features

- mechanism to automatically find and load Oakton commands from other assemblies through file scanning.
- "opts files"
  - inspired by Javascript tools like Mocha that use "opts" files to make their tools much easier to use at the command line

## Use cases

- Make it easy to embed and expose command help for user friendliness
- The power of Oakton really comes into play when it's combined with applications using the HostBuilder mechanism for bootstrapping .Net applications. See Integration with IHost for more information.
