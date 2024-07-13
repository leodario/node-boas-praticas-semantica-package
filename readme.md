# Good semantic practices in Script Names in package.json. Standardization.
[Official documentation](https://docs.npmjs.com/cli/v10/using-npm/scripts)

<u style="color: yellow">start</u>: Start the application.

<u style="color: yellow">dev</u>: Start the development server with hot reloading. build: Build the application for production.

<u style="color: yellow">test</u>: Run unit tests. test:watch: Run unit tests in watch mode. test:coverage: Generate test coverage report.

<u style="color: yellow">lint</u>: Lint the codebase. lint:fix: Fix linting errors automatically.

<u style="color: yellow">format</u>: Format code according to coding standards. clean: Clean up generated files.

<u style="color: yellow">precommit</u>: Run linting, formatting, and tests before committing code. deploy: Deploy the application to a server. analyze: Analyze the bundle size or performance of the application.

<u style="color: yellow">storybook</u>: Start Storybook for component development. storybook:build: Build Storybook for production. storybook:deploy: Deploy Storybook to a hosting service.

# Scripts do time do facebook no projeto do react
[https://github.com/facebook/react/blob/main/package.json](https://github.com/facebook/react/blob/main/package.json)
```
"scripts": {
    "build": "node ./scripts/rollup/build-all-release-channels.js",
    "build-for-devtools": "cross-env RELEASE_CHANNEL=experimental yarn build react/index,react/jsx,react/compiler-runtime,react-dom/index,react-dom/client,react-dom/unstable_testing,react-dom/test-utils,react-is,react-debug-tools,scheduler,react-test-renderer,react-refresh,react-art --type=NODE",
    "build-for-devtools-dev": "yarn build-for-devtools --type=NODE_DEV",
    "build-for-devtools-prod": "yarn build-for-devtools --type=NODE_PROD",
    "build-for-flight-dev": "cross-env RELEASE_CHANNEL=experimental node ./scripts/rollup/build.js react/index,react/jsx,react-dom/index,react-dom/client,react-dom/server,react-dom-server.node,react-dom-server-legacy.node,scheduler,react-server-dom-webpack/ --type=NODE_DEV && mv ./build/node_modules ./build/oss-experimental",
    "linc": "node ./scripts/tasks/linc.js",
    "lint": "node ./scripts/tasks/eslint.js",
    "lint-build": "node ./scripts/rollup/validate/index.js",
    "extract-errors": "node scripts/error-codes/extract-errors.js",
    "postinstall": "node node_modules/fbjs-scripts/node/check-dev-engines.js package.json && node ./scripts/flow/createFlowConfigs.js",
    "test": "node ./scripts/jest/jest-cli.js",
    "test-stable": "node ./scripts/jest/jest-cli.js --release-channel=stable",
    "test-www": "node ./scripts/jest/jest-cli.js --release-channel=www-modern",
    "test-classic": "node ./scripts/jest/jest-cli.js --release-channel=www-classic",
    "test-build-devtools": "node ./scripts/jest/jest-cli.js --build --project devtools --release-channel=experimental",
    "test-dom-fixture": "cd fixtures/dom && yarn && yarn test",
    "flow": "node ./scripts/tasks/flow.js",
    "flow-ci": "node ./scripts/tasks/flow-ci.js",
    "prettier": "node ./scripts/prettier/index.js write-changed",
    "prettier-all": "node ./scripts/prettier/index.js write",
    "prettier-check": "node ./scripts/prettier/index.js",
    "version-check": "node ./scripts/tasks/version-check.js",
    "publish-prereleases": "node ./scripts/release/publish-using-ci-workflow.js",
    "download-build": "node ./scripts/release/download-experimental-build.js",
    "download-build-for-head": "node ./scripts/release/download-experimental-build.js --commit=$(git rev-parse HEAD)",
    "download-build-in-codesandbox-ci": "cd scripts/release && yarn install && cd ../../ && yarn download-build-for-head || yarn build --type=node react/index react-dom/index react-dom/src/server react-dom/test-utils scheduler/index react/jsx-runtime react/jsx-dev-runtime",
    "check-release-dependencies": "node ./scripts/release/check-release-dependencies",
    "generate-inline-fizz-runtime": "node ./scripts/rollup/generate-inline-fizz-runtime.js",
    "flags": "node ./scripts/flags/flags.js"
  },
```