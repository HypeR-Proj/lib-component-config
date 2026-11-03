<!--
SPDX-FileCopyrightText: 2026 roolrz
SPDX-License-Identifier: Apache-2.0
-->

# lib-component-config

Bounded component declarations and capability routing rules.

Parses and validates component configuration without kernel bindings. Image composition
and runtime admission use the same declaration and routing vocabulary before any live
capability transfer.

See the [implementation entry](src/lib.rs) and [component declaration](component.json)
for the public interfaces, build dependencies and delivered artifacts.

## Boundaries

A valid declaration is not authority. Runtime owners must still resolve handles, check
rights and publish prepared processes through the kernel contracts.

## Build and test

Use this checkout inside the [repo-managed workspace](https://github.com/HypeR-Proj/HypeR).
From this repository directory:

```sh
make
make test
```

An absolute `OUT=/path/to/out` selects a shared output directory. The module
entry delegates to build/system, which prepares the installed SDK and declared
dependencies. Native binaries require HypeR; host module checks cover the tests
selected by component.json. A standalone clone does not contain the workspace’s
other source repositories or Native SDK.
