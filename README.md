# [Speckle](https://speckle.works) OpenApi Documentation

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1319026.svg)](https://doi.org/10.5281/zenodo.1319026)

View these docs [here](https://speckleworks.github.io/SpeckleSpecs/).

## Build

1. `npm install`
2. `npm run build`

## Build explanation

1. `swagger-cli bundle`: This resolves all the references and bundles up the schemas into `#/components/schemas`.
2. `widdershins`: This converts into a `md` file for use by `shins`.
3. `shins`: This converts the `md` file into a single `html` file.

## Deploy

If you push to the `master` branch, Travis will build and push the artifacts to the `gh-pages` branch.
