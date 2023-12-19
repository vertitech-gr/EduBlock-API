# Edublock SDK

A Javascript library for working with Verifiable Credentials, DIDs, Claim Deduction and more. Built with PolkadotJS, for use with the [Substrate Node]or our public main/test networks.

## build
- When building from source:
    - Run `yarn` to install the dependencies
    - Run `yarn build` to create a distribution version.


Running dev node:
```
./target/release/dock-node --base-path /tmp/alice --chain local_poa_testnet --alice --port 30333 --ws-port 9944 --rpc-port 9933 --telemetry-url 'wss://telemetry.polkadot.io/submit/ 0'
```

**Use the `mainnet` tag of this repo when interacting with mainnet as the `master` branch isn't guaranteed to be mainnet compatible.**

## Test and example Configuration
Configuration variables like websocket endpoint for node `FullNodeEndpoint`, URI for account to pay for extrinsics `TestAccountURI`
and keyring type `TestKeyringType` can be set as environment variables (or in an .env file). If they are not set, default values as
specified in file [test-constants.js](./tests/test-constants.js) are used.
The scripts read parameters from `.env` file. The available parameters are shown in an example env file [env_example](env_example)

## Test

Run unit tests with `yarn test`.

Run a single unit test module with `yarn test <module name or prefix>`.

Run e2e integrations tests with `yarn test-integration` (required node to be running)

You can run tests against a temporary node in docker like so:

```
./scripts/with_docker_test_node
yarn test-integration
```

or with the alias:

```
yarn test-with-node
```

and examples can be similarly run with:

```
yarn examples-with-node
```

## Linting and type checking
We use JSDoc and TypeScript for static type checking during the CI process. PRs must pass linting and type checking to be accepted.
You can run via: `yarn lint --fix` and `yarn type-check`
