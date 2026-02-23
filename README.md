# Laioutr App Commercetools

[![Laioutr][laioutr-src]][laioutr-href]
[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![License][license-src]][license-href]
[![Nuxt][nuxt-src]][nuxt-href]

Commercetools integration for [Laioutr](https://laioutr.com) frontends using Nuxt. Connects to the Commercetools Platform API via the orchestr system, enabling backend-agnostic ecommerce functionality.

> **[Read the full documentation](https://docs.laioutr.io/apps/app-docs/commercetools)**

- [Release Notes](/CHANGELOG.md)

## Features

- Anonymous and client credentials authentication flows with secure cookie-based token caching
- Product queries by slug and category with variant resolution
- Cart management with line item support
- Menu and category browsing
- Faceted search with customizable filters and sorting
- Canonical type resolvers for Cart, MenuItem, Product, and ProductVariant

## Quick Setup

Before installing dependencies, you need to create a copy of the `.npmrc.config` file called `.npmrc` and fill in the `NPM_LAIOUTR_TOKEN` with your npm token. You can find this token in your [project settings](https://cockpit.laioutr.cloud/o/_/p/_/settings).

- `pnpm i`
- `npx @laioutr/cli project fetch-rc -p <organization slug>/<project slug> -s <project secret key>` - This will load the `laioutrrc.json` file with the current remote project configuration.
- `pnpm dev:prepare`
- `pnpm orchestr-dev`

That's it! You can now use the Commercetools App in your [Laioutr Frontend](https://laioutr.com).

You can find a thorough guide on getting started with Laioutr development in our [developer guide](https://docs.laioutr.io/developer-guide/setup).

## Commercetools Prerequisites

You will need the following from the Commercetools Merchant Center:

- **Project Key**
- **API URL** and **Auth URL** (region-specific)
- **Client ID** and **Client Secret**

Your Commercetools project should have:

- Published products with locale-specific slugs
- Categories with keys and slugs
- Inventory/availability configured
- Searchable attributes marked in product types
- Anonymous sessions enabled (for guest cart functionality)

For detailed configuration instructions, see the [documentation](https://docs.laioutr.io/apps/app-docs/commercetools).

## Linting and Formatting

We use ESLint and Prettier to lint and format the code. This repository contains opinionated configurations for both tools. You can replace them with your own configurations.

## Publishing

To publish a new version, run `pnpm release`. This will:

- Run the tests
- Update the changelog
- Publish the package to npmjs.org
- Push the changes to the repository

### Private publishing

If you want to publish a private package to npm.laioutr.cloud, you need to:

1. Make sure you have a `.npmrc` with your private npm registry token.
2. Add this line to the root of the `package.json` file: `"publishConfig": { "registry": "https://npm.laioutr.cloud/" }`
3. Make sure your package-name follows the `@laioutr-org/<organization-slug>_<package-name>` format.

After that you can run `pnpm release` to publish the package to npm.laioutr.cloud.

## Contribution

Follow the [setup guide](https://docs.laioutr.io/developer-guide/setup) to get started.

<!-- Badges -->

[npm-version-src]: https://img.shields.io/npm/v/@laioutr-app/commercetools/latest.svg?style=flat&colorA=020420&colorB=00DC82
[npm-version-href]: https://npmjs.com/package/@laioutr-app/commercetools
[npm-downloads-src]: https://img.shields.io/npm/dm/@laioutr-app/commercetools.svg?style=flat&colorA=020420&colorB=00DC82
[npm-downloads-href]: https://npm.chart.dev/@laioutr-app/commercetools
[license-src]: https://img.shields.io/npm/l/@laioutr-app/commercetools.svg?style=flat&colorA=020420&colorB=00DC82
[license-href]: https://npmjs.com/package/@laioutr-app/commercetools
[nuxt-src]: https://img.shields.io/badge/Nuxt-020420?logo=nuxt.js
[nuxt-href]: https://nuxt.com
[laioutr-src]: https://img.shields.io/badge/%F0%9F%A6%99_Laioutr_App-702DCE
[laioutr-href]: https://www.laioutr.com/
