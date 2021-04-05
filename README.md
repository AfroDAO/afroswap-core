# Afroswap 

[![Lint](https://github.com/afroswap/afroswap-core/actions/workflows/lint.yml/badge.svg)](https://github.com/afroswap/afroswap-core/actions/workflows/lint.yml)
[![Tests](https://github.com/afroswap/afroswap-core/actions/workflows/tests.yml/badge.svg)](https://github.com/afroswap/afroswap-core/actions/workflows/tests.yml)
[![Fuzz Testing](https://github.com/afroswap/afroswap-core/actions/workflows/fuzz-testing.yml/badge.svg)](https://github.com/afroswap/afroswap-core/actions/workflows/fuzz-testing.yml)
[![Mythx](https://github.com/afroswap/afroswap-core/actions/workflows/mythx.yml/badge.svg)](https://github.com/afroswap/afroswap-core/actions/workflows/mythx.yml)
[![npm version](https://img.shields.io/npm/v/@afroswap/core/latest.svg)](https://www.npmjs.com/package/@afroswap/-core/v/latest)

This repository contains the core smart contracts for the afroswap  Protocol.
For higher level contracts, see the [afroswap-periphery](https://github.com/afroswap/afroswap-periphery)
repository.

## Bug bounty

This repository is subject to the afroswap  bug bounty program, per the terms defined [here](./bug-bounty.md).

## Local deployment

In order to deploy this code to a local testnet, you should install the npm package
`@afroswap/core`
and import the factory bytecode located at
`@afroswap/core/artifacts/contracts/afroswapFactory.sol/afroswapFactory.json`.
For example:

```typescript
import {
  abi as FACTORY_ABI,
  bytecode as FACTORY_BYTECODE,
} from '@afroswap/core/artifacts/contracts/afroswapFactory.sol/afroswapFactory.json'

// deploy the bytecode
```

This will ensure that you are testing against the same bytecode that is deployed to
mainnet and public testnets, and all afroswap code will correctly interoperate with
your local deployment.

## Using solidity interfaces

The afroswap  interfaces are available for import into solidity smart contracts
via the npm artifact `@afroswap/core`, e.g.:

```solidity
import '@afroswap/core/contracts/interfaces/IafroswapPool.sol';

contract MyContract {
  IafroswapPool pool;

  function doSomethingWithPool() {
    // pool.swap(...);
  }
}

```

## Licensing

The primary license for afroswap  Core is the Business Source License 1.1 (`BUSL-1.1`), see [`LICENSE`](./LICENSE).

### Exceptions

- All files in `contracts/interfaces/` are licensed under `GPL-2.0-or-later` (as indicated in their SPDX headers), see [`contracts/interfaces/LICENSE`](./contracts/interfaces/LICENSE)
- Several files in `contracts/libraries/` are licensed under `GPL-2.0-or-later` (as indicated in their SPDX headers), see [`contracts/libraries/LICENSE_GPL`](contracts/libraries/LICENSE_GPL)
- `contracts/libraries/FullMath.sol` is licensed under `MIT` (as indicated in its SPDX header), see [`contracts/libraries/LICENSE_MIT`](contracts/libraries/LICENSE_MIT)
- All files in `contracts/test` remain unlicensed.
