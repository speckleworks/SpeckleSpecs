# [Speckle.Works](http://spekcle.works) OpenApi Documentation

### Generate the spec:
Install `multi-file-swagger`:

```javascript
  npm install -g multi-file-swagger
```

Run the command like so:

```javascript
  multi-file-swagger index.yaml > index.json
```

This will resolve every json pointer ($ref) externally or internally and then save it in a json file. Which can then be used for code generation and so on.

### Visualise the spec:

Head over to [the swagger editor](http://editor.swagger.io) and drop in the generated index.json. 

### Generate code from the spec:
Either use `swagger-codegen` or simply export from the editor your client of choice.

#### License
MIT
