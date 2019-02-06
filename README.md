# [Speckle](https://speckle.works) OpenApi Documentation
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1319026.svg)](https://doi.org/10.5281/zenodo.1319026)

This is a work in progress branch, migrating from [OpenApi 2.0](./SpeckleV1OpenApiSpecs.yaml) to [OpenApi 3.0.2](./SpeckleSpecs.yaml).

## Build

Because the spec may be split across several files using `$ref`, we have an extra step to resolve and bundle up the references. I can't manage to make "widdershins" do this properly, so I use "swagger-cli bundle" to resolve references and bundle them all into "/components/schemas".

1. `npm install`
2. `npm run build`
