# [Speckle](https://speckle.works) OpenApi Documentation
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1319026.svg)](https://doi.org/10.5281/zenodo.1319026)


> [docs](https://speckleworks.github.io/SpeckleSpecs/)

# Visualise & Edit

Open the `SpeckleV1OpenApiSpecs.yaml` file in the [OpenApi editor](https://editor.swagger.io//#/). You can then edit at your own ease, and suggest changes, etc.

# Local build

To build the docs locally, please follow these quick steps:

1. `npm install`
2. `(cd shins && npm install)`
3. `npm run build-shins` - this will generate the docs

# Commit

The html rendering is produced by Travis. If you're pushing to the `master` branch, Travis will try to deploy the contents of the docs directory to the `gh-pages` branch.

That's it! 
