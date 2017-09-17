---
title: SpeckleCore v0.0.3
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
---

# SpeckleCore v0.0.3

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Documentation & specifications for the Speckle Server & Speckle Objects.

https://speckle.works

This OAS doc for Speckle. It does *not* cover the realtime communication layer (websockets).

There are two main parts you should look at:
### 1. Operations
This section describes all the available `operations` that the speckle server can perform, revolving around a simple `Accounts` system, `Clients` (keeping track of all the receivers and senders), `Streams`, `Stream Layers`, `Stream Objects` and `Objects`.

### 2. Schema Defintions
This section describes the basic building blocks that Speckle works with. It also contains an extensive list of `Payloads` and `Responses` which are less interesting, but a through look at the `SpeckleObject` and its children is needed, especially if you're looking into implementing your own application specific converter. 

Base URLs:

* <a href="http://localhost:8080/api">http://localhost:8080/api</a>

* <a href="https://localhost:8080/api">https://localhost:8080/api</a>



Email: <a href="mailto:didimitrie@gmail.com">SpeckleWorks</a> Web: <a href="https://speckle.works">SpeckleWorks</a> 
 License: MIT

# Authentication


* API Key
    - Parameter Name: **Authorization**, in: header. 



# Accounts

Register, Login and Get/Set user profiles.

## UserRegister

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/accounts/register \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/accounts/register HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/register',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "email": "string",
  "password": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/register',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/accounts/register',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/accounts/register', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/register");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /accounts/register`

*UserRegister*

Registers a new user.

> Body parameter

```json
{
  "email": "string",
  "password": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[PayloadAccountRegister](#schemapayloadaccountregister)|true|No description
» email|body|string|true|No description
» password|body|string|true|No description
» name|body|string|false|No description
» surname|body|string|false|No description
» company|body|string|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "token": "string",
  "apiToken": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseAccountRegister](#schemaresponseaccountregister)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed to register a new user.|[ResponseBase](#schemaresponsebase)

<aside class="success">
This operation does not require authentication
</aside>

## UserLogin

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/accounts/login \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/accounts/login HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/login',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "email": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/login',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/accounts/login',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/accounts/login', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/login");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /accounts/login`

*UserLogin*

Login and get jwt token.

> Body parameter

```json
{
  "email": "string",
  "password": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[PayloadAccountLogin](#schemapayloadaccountlogin)|true|No description
» email|body|string|true|No description
» password|body|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "token": "string",
  "apiToken": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseAccountLogin](#schemaresponseaccountlogin)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="success">
This operation does not require authentication
</aside>

## UserStreamsGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/accounts/streams \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/accounts/streams HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/streams',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/streams',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/accounts/streams',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/accounts/streams', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/streams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /accounts/streams`

*UserStreamsGet*

Gets all the streams for a user (identified via the authorization token, so if that is s not present, it will not work).

> Example responses

```json
{
  "success": true,
  "message": "string",
  "streams": [
    {
      "_id": "string",
      "streamId": "string",
      "owner": "string",
      "private": false,
      "name": "Anonymous Stream",
      "objects": [
        {
          "type": "Boolean",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {}
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "0;0;0;0-2 0;0;0;1-2",
          "properties": {
            "color": {
              "a": 1,
              "hex": "#d4d4d4"
            },
            "visible": true,
            "pointsize": 0,
            "linewidth": 0,
            "shininess": 0,
            "smooth": true,
            "showEdges": true,
            "wireframe": true
          }
        }
      ],
      "parent": "string",
      "children": [
        "string"
      ]
    }
  ],
  "sharedStreams": [
    {
      "_id": "string",
      "streamId": "string",
      "owner": "string",
      "private": false,
      "name": "Anonymous Stream",
      "objects": [
        {
          "type": "Boolean",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {}
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "0;0;0;0-2 0;0;0;1-2",
          "properties": {
            "color": {
              "a": 1,
              "hex": "#d4d4d4"
            },
            "visible": true,
            "pointsize": 0,
            "linewidth": 0,
            "shininess": 0,
            "smooth": true,
            "showEdges": true,
            "wireframe": true
          }
        }
      ],
      "parent": "string",
      "children": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseAccountStreams](#schemaresponseaccountstreams)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserClientsGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/accounts/clients \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/accounts/clients HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/clients',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/clients',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/accounts/clients',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/accounts/clients', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/clients");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /accounts/clients`

*UserClientsGet*

Gets all the clients for a user (identified via the authorization token, so if that is s not present, it will not work).

> Example responses

```json
{
  "success": true,
  "message": "string",
  "clients": [
    {
      "_id": "string",
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "streamId": "string",
      "owner": "string",
      "online": true
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseAccountClients](#schemaresponseaccountclients)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserGetProfile

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/accounts/profile \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/accounts/profile HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/profile',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/profile',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/accounts/profile',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/accounts/profile', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/profile");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /accounts/profile`

*UserGetProfile*

Gets the user's profile.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "user": {
    "_id": "string",
    "apitoken": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseAccountProfile](#schemaresponseaccountprofile)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/accounts/profile \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/accounts/profile HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/accounts/profile',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/accounts/profile',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/accounts/profile',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/accounts/profile', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/accounts/profile");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /accounts/profile`

*UserUpdate*

TODO. Should update user profile with new information.

> Body parameter

```json
{
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[PayloadAccountUpdate](#schemapayloadaccountupdate)|true|No description
» email|body|string|false|No description
» name|body|string|false|No description
» surname|body|string|false|No description
» company|body|string|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Clients

Create, get and update application clients. Without one you can't send/receive/broadcast websocket messages.

## ClientCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/clients \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/clients HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/clients',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "client": {
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/clients',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/clients',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/clients', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/clients");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /clients`

*ClientCreate*

Creates a new client and returns your `clientId`. If not authorised, you get a temporary `clientId`.

> Body parameter

```json
{
  "client": {
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string"
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[PayloadClientCreate](#schemapayloadclientcreate)|true|No description
» client|body|object|false|No description
»» role|body|string|false|No description
»» documentGuid|body|string|false|No description
»» documentName|body|string|false|No description
»» documentType|body|string|false|No description
»» streamId|body|string|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "clientId": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully creates a new client.|[ResponseClientCreate](#schemaresponseclientcreate)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/clients/{clientId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/clients/{clientId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/clients/{clientId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/clients/{clientId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/clients/{clientId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/clients/{clientId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /clients/{clientId}`

*ClientGet*

Gets a client.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|the client's id.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "client": {
    "_id": "string",
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string",
    "owner": "string",
    "online": true
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Client got.|[ResponseClientGet](#schemaresponseclientget)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/clients/{clientId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/clients/{clientId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/clients/{clientId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "client": {
    "_id": "string",
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string",
    "owner": "string",
    "online": true
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/clients/{clientId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/clients/{clientId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/clients/{clientId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /clients/{clientId}`

*ClientUpdate*

Updates a client.

> Body parameter

```json
{
  "client": {
    "_id": "string",
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string",
    "owner": "string",
    "online": true
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|the client's id.
body|body|[PayloadClientUpdate](#schemapayloadclientupdate)|true|No description
» client|body|[SpeckleClient](#schemaspeckleclient)|false|A representation of the manifestation of a Speckle Client. Whenever an instance of a client is born in any software, it should get its matching identity on the server. When deserialising itself, it should call back to the database and set itself as online. Its uuid sould server as sessionId for the websocket client.
»» _id|body|string|false|Database uuid.
»» role|body|string|false|Sender, Receiver, Mixed (for both), Parametric Sender if it can operate on parameters inside a defintion, or whatever else we can think of.
»» documentGuid|body|string|false|No description
»» documentName|body|string|false|No description
»» documentType|body|string|false|No description
»» streamId|body|string|false|The streamId that this clients 'listens to'.
»» owner|body|string|false|No description
»» online|body|boolean|false|Is it accessible from the server or not?


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/clients/{clientId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/clients/{clientId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/clients/{clientId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/clients/{clientId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/clients/{clientId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/clients/{clientId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /clients/{clientId}`

*ClientDelete*

Marks a client for deletion.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|the client's id.


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Computer is benevolent.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Computer is confused.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Computer says you're not authorised.|[ResponseBase](#schemaresponsebase)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Computer can't find shit.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Streams

Create, get and update streams.

## StreamCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/streams \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/streams HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/streams',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/streams', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /streams`

*StreamCreate*

Creates a new stream.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "stream": {
    "_id": "string",
    "streamId": "string",
    "owner": "string",
    "private": false,
    "name": "Anonymous Stream",
    "objects": [
      {
        "type": "Boolean",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {}
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "parent": "string",
    "children": [
      "string"
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Initialises a stream in the db. You get back the 'streamId'.|[ResponseStreamCreate](#schemaresponsestreamcreate)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}`

*StreamGet*

Will return the specified stream. If no `Authorization` header is provided and the stream is private you will get a 401. It populates the `objects` array fully. If you want a light version of the stream, query `/api/streams/{streamId}/meta`.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|The stream's id.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "stream": {
    "_id": "string",
    "streamId": "string",
    "owner": "string",
    "private": false,
    "name": "Anonymous Stream",
    "objects": [
      {
        "type": "Boolean",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {}
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "parent": "string",
    "children": [
      "string"
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponseStreamGet](#schemaresponsestreamget)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Stream not found.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ],
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}`

*StreamUpdate*

Updates the stream.

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ],
  "name": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|The stream's id.
body|body|[PayloadStreamUpdate](#schemapayloadstreamupdate)|true|No description
» name|body|string|false|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.
»» type|body|string|true|object's type
»» hash|body|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|body|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|body|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|body|object|false|Anything goes in here, including other (speckle) objects.
»» type|body|Unknown|false|No description
»» description|body|Unknown|false|No description
» layers|body|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|body|string|false|Layer's name
»» guid|body|string|false|Layer's guid (must be unique)
»» orderIndex|body|integer|false|Describes this layer's position in the list of layers.
»» startIndex|body|number|false|The index of the first object relative to the stream's objects array
»» objectCount|body|number|false|How many objects does this layer have.
»» topology|body|string|false|String describing the nested tree structure (Gh centric).
»» properties|body|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|body|object|false|No description
»»»» a|body|number|false|alpha value
»»»» hex|body|string|false|hex color value
»»» visible|body|boolean|false|toggles layer visibility.
»»» pointsize|body|number|false|defines point size in threejs
»»» linewidth|body|number|false|defines line thickness in threejs
»»» shininess|body|number|false|says it all. speckle is superficial.
»»» smooth|body|boolean|false|smooth shading toggle
»»» showEdges|body|boolean|false|display edges or not yo.
»»» wireframe|body|boolean|false|i'm bored.
»» properties|body|Unknown|false|No description
»» description|body|Unknown|false|No description
»» x-old-ref|body|Unknown|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|

##### » objects
Base class that is inherited by all other Speckle objects. The only required value is its `type`.

Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|On success|[ResponseStreamUpdate](#schemaresponsestreamupdate)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Status 401|[ResponseBase](#schemaresponsebase)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Status 404|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}`

*StreamDelete*

Flags stream for deletion.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|The stream's id.


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamGetName

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/name \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/name HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/name',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/name',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/name',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/name', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/name");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/name`

*StreamGetName*

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "name": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseStreamNameGet](#schemaresponsestreamnameget)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamUpdateName

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId}/name \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId}/name HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/name',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/name',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}/name',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}/name', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/name");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}/name`

*StreamUpdateName*

> Body parameter

```json
{
  "name": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[PayloadStreamNameUpdate](#schemapayloadstreamnameupdate)|true|No description
» name|body|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Stream Layers Collection

Modify the stream's layer collection.

## GetLayers

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/layers \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/layers HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/layers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/layers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/layers`

*GetLayers*

Retrieves the stream's layers.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseStreamLayersGet](#schemaresponsestreamlayersget)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## AddLayers

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/streams/{streamId}/layers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/streams/{streamId}/layers HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "layers": [
    {}
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/streams/{streamId}/layers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/streams/{streamId}/layers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /streams/{streamId}/layers`

*AddLayers*

Adds the provided layers to the stream.

> Body parameter

```json
{
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[AddLayersBody](#schema+addlayersbody)|true|No description
» layers|body|[[SpeckleLayer](#schemaspecklelayer)]|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ReplaceLayers

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId}/layers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId}/layers HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}/layers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}/layers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}/layers`

*ReplaceLayers*

Updates stream layers.

> Body parameter

```json
{
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[AddLayersBody](#schema+addlayersbody)|true|No description
» layers|body|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|body|string|false|Layer's name
»» guid|body|string|false|Layer's guid (must be unique)
»» orderIndex|body|integer|false|Describes this layer's position in the list of layers.
»» startIndex|body|number|false|The index of the first object relative to the stream's objects array
»» objectCount|body|number|false|How many objects does this layer have.
»» topology|body|string|false|String describing the nested tree structure (Gh centric).
»» properties|body|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|body|object|false|No description
»»»» a|body|number|false|alpha value
»»»» hex|body|string|false|hex color value
»»» visible|body|boolean|false|toggles layer visibility.
»»» pointsize|body|number|false|defines point size in threejs
»»» linewidth|body|number|false|defines line thickness in threejs
»»» shininess|body|number|false|says it all. speckle is superficial.
»»» smooth|body|boolean|false|smooth shading toggle
»»» showEdges|body|boolean|false|display edges or not yo.
»»» wireframe|body|boolean|false|i'm bored.
»» type|body|Unknown|false|No description
»» properties|body|Unknown|false|No description
»» description|body|Unknown|false|No description
»» x-old-ref|body|Unknown|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## MergeLayers

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/streams/{streamId}/layers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:8080/api/streams/{streamId}/layers HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:8080/api/streams/{streamId}/layers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:8080/api/streams/{streamId}/layers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PATCH /streams/{streamId}/layers`

*MergeLayers*

Merges the stream layers. Gently. And with lots of tender care.

> Body parameter

```json
{
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[AddLayersBody](#schema+addlayersbody)|true|No description
» layers|body|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|body|string|false|Layer's name
»» guid|body|string|false|Layer's guid (must be unique)
»» orderIndex|body|integer|false|Describes this layer's position in the list of layers.
»» startIndex|body|number|false|The index of the first object relative to the stream's objects array
»» objectCount|body|number|false|How many objects does this layer have.
»» topology|body|string|false|String describing the nested tree structure (Gh centric).
»» properties|body|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|body|object|false|No description
»»»» a|body|number|false|alpha value
»»»» hex|body|string|false|hex color value
»»» visible|body|boolean|false|toggles layer visibility.
»»» pointsize|body|number|false|defines point size in threejs
»»» linewidth|body|number|false|defines line thickness in threejs
»»» shininess|body|number|false|says it all. speckle is superficial.
»»» smooth|body|boolean|false|smooth shading toggle
»»» showEdges|body|boolean|false|display edges or not yo.
»»» wireframe|body|boolean|false|i'm bored.
»» type|body|Unknown|false|No description
»» properties|body|Unknown|false|No description
»» description|body|Unknown|false|No description
»» x-old-ref|body|Unknown|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## DeleteLayers

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId}/layers \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId}/layers HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}/layers',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}/layers', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}/layers`

*DeleteLayers*

Purges the stream's layer list.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Stream Layer

Modify a stream's specific layer.

## GetSingleLayer

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/layers/{layerId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/layers/{layerId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/layers/{layerId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/layers/{layerId}`

*GetSingleLayer*

Retrieves a stream layer.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "layer": {
    "name": "string",
    "guid": "string",
    "orderIndex": 0,
    "startIndex": 0,
    "objectCount": 0,
    "topology": "0;0;0;0-2 0;0;0;1-2",
    "properties": {
      "color": {
        "a": 1,
        "hex": "#d4d4d4"
      },
      "visible": true,
      "pointsize": 0,
      "linewidth": 0,
      "shininess": 0,
      "smooth": true,
      "showEdges": true,
      "wireframe": true
    }
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful whale.|[ResponseSingleLayer](#schemaresponsesinglelayer)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ReplaceSingleLayer

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId}/layers/{layerId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId}/layers/{layerId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "layer": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}/layers/{layerId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}/layers/{layerId}`

*ReplaceSingleLayer*

Overwrites a stream layer.

> Body parameter

```json
{
  "layer": {
    "name": "string",
    "guid": "string",
    "orderIndex": 0,
    "startIndex": 0,
    "objectCount": 0,
    "topology": "0;0;0;0-2 0;0;0;1-2",
    "properties": {
      "color": {
        "a": 1,
        "hex": "#d4d4d4"
      },
      "visible": true,
      "pointsize": 0,
      "linewidth": 0,
      "shininess": 0,
      "smooth": true,
      "showEdges": true,
      "wireframe": true
    }
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
body|body|[ReplaceSingleLayerBody](#schema+replacesinglelayerbody)|true|No description
» layer|body|[SpeckleLayer](#schemaspecklelayer)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful whale.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UpdateSingleLayer

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:8080/api/streams/{streamId}/layers/{layerId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:8080/api/streams/{streamId}/layers/{layerId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "layer": {
    "name": "string",
    "guid": "string",
    "orderIndex": 0,
    "startIndex": 0,
    "objectCount": 0,
    "topology": "0;0;0;0-2 0;0;0;1-2",
    "properties": {
      "color": {
        "a": 1,
        "hex": "#d4d4d4"
      },
      "visible": true,
      "pointsize": 0,
      "linewidth": 0,
      "shininess": 0,
      "smooth": true,
      "showEdges": true,
      "wireframe": true
    }
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PATCH /streams/{streamId}/layers/{layerId}`

*UpdateSingleLayer*

Updates a stream layer (merges keys).

> Body parameter

```json
{
  "layer": {
    "name": "string",
    "guid": "string",
    "orderIndex": 0,
    "startIndex": 0,
    "objectCount": 0,
    "topology": "0;0;0;0-2 0;0;0;1-2",
    "properties": {
      "color": {
        "a": 1,
        "hex": "#d4d4d4"
      },
      "visible": true,
      "pointsize": 0,
      "linewidth": 0,
      "shininess": 0,
      "smooth": true,
      "showEdges": true,
      "wireframe": true
    }
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
body|body|[ReplaceSingleLayerBody](#schema+replacesinglelayerbody)|true|No description
» layer|body|[SpeckleLayer](#schemaspecklelayer)|true|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|body|string|false|Layer's name
»» guid|body|string|false|Layer's guid (must be unique)
»» orderIndex|body|integer|false|Describes this layer's position in the list of layers.
»» startIndex|body|number|false|The index of the first object relative to the stream's objects array
»» objectCount|body|number|false|How many objects does this layer have.
»» topology|body|string|false|String describing the nested tree structure (Gh centric).
»» properties|body|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|body|object|false|No description
»»»» a|body|number|false|alpha value
»»»» hex|body|string|false|hex color value
»»» visible|body|boolean|false|toggles layer visibility.
»»» pointsize|body|number|false|defines point size in threejs
»»» linewidth|body|number|false|defines line thickness in threejs
»»» shininess|body|number|false|says it all. speckle is superficial.
»»» smooth|body|boolean|false|smooth shading toggle
»»» showEdges|body|boolean|false|display edges or not yo.
»»» wireframe|body|boolean|false|i'm bored.
»» type|body|Unknown|false|No description
»» properties|body|Unknown|false|No description
»» description|body|Unknown|false|No description
»» x-old-ref|body|Unknown|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful whale.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## DeleteSingleLayer

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId}/layers/{layerId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId}/layers/{layerId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}/layers/{layerId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}/layers/{layerId}`

*DeleteSingleLayer*

Deletes a stream layer.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful whale.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Layer Objects Collection

Add, remove objects to a specific layer in the stream.

## GetLayerObjects

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/layers/{layerId}/objects`

*GetLayerObjects*

Gets the objects from a stream's layer.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
query|query|string|false|Filter by field values, get or omit specific fields & sort.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponseGetObjects](#schemaresponsegetobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## AddLayerObjects

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {}
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /streams/{streamId}/layers/{layerId}/objects`

*AddLayerObjects*

Adds objects to a stream's layer. Manages the layer collection's indexes (startIndex, objectCount).

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
body|body|[AddLayerObjectsBody](#schema+addlayerobjectsbody)|true|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponsePostObjects](#schemaresponsepostobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ReplaceLayerObjects

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}/layers/{layerId}/objects`

*ReplaceLayerObjects*

Replaces the layer's objects.

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
body|body|[AddLayerObjectsBody](#schema+addlayerobjectsbody)|true|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.
»» type|body|string|true|object's type
»» hash|body|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|body|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|body|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|body|object|false|Anything goes in here, including other (speckle) objects.
»» type|body|Unknown|false|No description
»» description|body|Unknown|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|

##### » objects
Base class that is inherited by all other Speckle objects. The only required value is its `type`.

Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponsePostObjects](#schemaresponsepostobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## DeleteLayerObjects

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
{
  method: 'DELETE',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/layers/{layerId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}/layers/{layerId}/objects`

*DeleteLayerObjects*

Deletes the layer's objects. If you provide a list of ids, it will delete just those.

> Body parameter

```json
{
  "objects": [
    "string"
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
layerId|path|string|true|Layer guid or name. In case of name, the first layer of that name is selected.
body|body|object|false|No description
» objects|body|[string]|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success whale.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Stream Objects Collection

Directly operate on the objects in the stream.

## GetObjects

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/objects \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/objects HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/objects',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/objects',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/objects`

*GetObjects*

Retrieves the stream's objects.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
query|query|string|false|Filter by field values, get or omit specific fields & sort.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseStreamLayersGet](#schemaresponsestreamlayersget)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## AddObjects

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/streams/{streamId}/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/streams/{streamId}/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/objects',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {}
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/objects',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/streams/{streamId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/streams/{streamId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /streams/{streamId}/objects`

*AddObjects*

Adds the provided objects to the stream.

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[AddObjectsBody](#schema+addobjectsbody)|true|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponsePostObjects](#schemaresponsepostobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ReplaceObjects

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/streams/{streamId}/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/streams/{streamId}/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/objects',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/objects',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/streams/{streamId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/streams/{streamId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /streams/{streamId}/objects`

*ReplaceObjects*

Updates stream layers.

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[AddObjectsBody](#schema+addobjectsbody)|true|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.
»» type|body|string|true|object's type
»» hash|body|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|body|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|body|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|body|object|false|Anything goes in here, including other (speckle) objects.
»» type|body|Unknown|false|No description
»» description|body|Unknown|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|

##### » objects
Base class that is inherited by all other Speckle objects. The only required value is its `type`.

Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponsePostObjects](#schemaresponsepostobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## DeleteObjects

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId}/objects \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId}/objects HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/objects',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/objects',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}/objects`

*DeleteObjects*

Purges the stream's object list.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectDeleteFromStream

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/streams/{streamId}/objects/{objectId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/streams/{streamId}/objects/{objectId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/objects/{objectId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/objects/{objectId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/streams/{streamId}/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/streams/{streamId}/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/objects/{objectId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /streams/{streamId}/objects/{objectId}`

*ObjectDeleteFromStream*

Deletes the specified object from the stream's object list.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
objectId|path|string|true|The `objectId` that you want to remove.


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Woot! Operation succeeded!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Special Ops

Extra lvl 5 magic spells.

## StreamClone

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/streams/{streamId}/clone \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/streams/{streamId}/clone HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/clone',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/clone',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/streams/{streamId}/clone',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/streams/{streamId}/clone', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/clone");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /streams/{streamId}/clone`

*StreamClone*

Clones the current stream, saving the clone to the children array of the parent, and saving the parent to the parent field of the clone. This operation exists to enable various versioning/history operations for design variants. 

For example, you can use it to save the current state as an option, similar to the traditional `Save As > 0087QPT-FacadeVersionXX.3dm`. 

Alternatively, you can use it to branch off from the current state, by switching all future updates to the clone's stream.

Sky & UI's the limit.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|The stream's id.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "clone": {
    "_id": "string",
    "streamId": "string"
  },
  "parent": {
    "_id": "string",
    "streamId": "string",
    "children": [
      "string"
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseStreamClone](#schemaresponsestreamclone)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamDiff

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/streams/{streamId}/diff/{otherId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/streams/{streamId}/diff/{otherId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/streams/{streamId}/diff/{otherId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/streams/{streamId}/diff/{otherId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/streams/{streamId}/diff/{otherId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/streams/{streamId}/diff/{otherId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/streams/{streamId}/diff/{otherId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /streams/{streamId}/diff/{otherId}`

*StreamDiff*

Diffs two streams, by objects and layers.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|The stream's id.
otherId|path|string|true|The stream you want to diff against.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": {
    "common": [
      "string"
    ],
    "inA": [
      "string"
    ],
    "inB": [
      "string"
    ]
  },
  "layers": {
    "common": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "inA": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "inB": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseStreamDiff](#schemaresponsestreamdiff)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Objects

Directly CRUD objects in the database. They are not part of streams, and, as such, kindof suck.

## ObjectCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/objects HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/objects',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/objects',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/objects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /objects`

*ObjectCreate*

Creates an object.

> Body parameter

```json
{
  "object": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|object|true|No description
» object|body|[SpeckleObject](#schemaspeckleobject)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseObjectCreate](#schemaresponseobjectcreate)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/api/objects/{objectId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:8080/api/objects/{objectId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/objects/{objectId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/objects/{objectId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:8080/api/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:8080/api/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/objects/{objectId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`GET /objects/{objectId}`

*ObjectGet*

Gets a SpeckleObject from the database.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description
query|query|string|false|Specify which fields to retrieve or omit.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "speckleObject": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Object found|[ResponseObjectGet](#schemaresponseobjectget)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Status 404|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/api/objects/{objectId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:8080/api/objects/{objectId} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/objects/{objectId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "object": {}
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/objects/{objectId}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:8080/api/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:8080/api/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/objects/{objectId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`PUT /objects/{objectId}`

*ObjectUpdate*

Updates an object by its id.

> Body parameter

```json
{
  "object": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description
body|body|object|true|No description
» object|body|[SpeckleObject](#schemaspeckleobject)|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponseObjectUpdate](#schemaresponseobjectupdate)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/api/objects/{objectId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:8080/api/objects/{objectId} HTTP/1.1
Host: localhost:8080

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/objects/{objectId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/objects/{objectId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:8080/api/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:8080/api/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/objects/{objectId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`DELETE /objects/{objectId}`

*ObjectDelete*

Flags an object for deletion.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Done deal yo!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectCreateBulk

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/api/objects/bulk \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:8080/api/objects/bulk HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:8080/api/objects/bulk',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:8080/api/objects/bulk',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:8080/api/objects/bulk',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:8080/api/objects/bulk', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:8080/api/objects/bulk");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

`POST /objects/bulk`

*ObjectCreateBulk*

Creates and stores in the database a SpeckleObject.

> Body parameter

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[AddLayerObjectsBody](#schema+addlayerobjectsbody)|true|No description
» objects|body|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.
»» type|body|string|true|object's type
»» hash|body|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|body|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|body|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|body|object|false|Anything goes in here, including other (speckle) objects.
»» type|body|Unknown|false|No description
»» description|body|Unknown|false|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|

##### » objects
Base class that is inherited by all other Speckle objects. The only required value is its `type`.

Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
> Example responses

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
}
```
```json
{
  "success": true,
  "message": "string"
}
```
```json
{
  "success": true,
  "message": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Status 200|[ResponsePostObjects](#schemaresponsepostobjects)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorised whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Schemas

## User

<a name="schemauser"></a>

```json
{
  "_id": "string",
  "apitoken": "string",
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string",
  "logins": [
    {
      "date": "string"
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
_id|string|false|Database uuid.
apitoken|string|false|a signed jwt token that expires in 1 year.
email|string|false|user's email
name|string|false|User's given name
surname|string|false|User's family name
company|string|false|Users's company
logins|[object]|false|it's a timestamp XD
» date|string|false|No description



## SpeckleClient

<a name="schemaspeckleclient"></a>

```json
{
  "_id": "string",
  "role": "string",
  "documentGuid": "string",
  "documentName": "string",
  "documentType": "string",
  "streamId": "string",
  "owner": "string",
  "online": true
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
_id|string|false|Database uuid.
role|string|false|Sender, Receiver, Mixed (for both), Parametric Sender if it can operate on parameters inside a defintion, or whatever else we can think of.
documentGuid|string|false|No description
documentName|string|false|No description
documentType|string|false|No description
streamId|string|false|The streamId that this clients 'listens to'.
owner|string|false|No description
online|boolean|false|Is it accessible from the server or not?



## DataStream

<a name="schemadatastream"></a>

```json
{
  "_id": "string",
  "streamId": "string",
  "owner": "string",
  "private": false,
  "name": "Anonymous Stream",
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ],
  "parent": "string",
  "children": [
    "string"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
_id|string|false|Database uuid.
streamId|string|true|The stream's short id.
owner|string|false|The owner's user id.
private|boolean|false|No description
name|string|true|The data stream's name
parent|string|false|Parent stream's id, if any. If null, this is a `root` stream.
objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
» name|string|false|Layer's name
» guid|string|false|Layer's guid (must be unique)
» orderIndex|integer|false|Describes this layer's position in the list of layers.
» startIndex|number|false|The index of the first object relative to the stream's objects array
» objectCount|number|false|How many objects does this layer have.
» topology|string|false|String describing the nested tree structure (Gh centric).
» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»» color|object|false|No description
»»» a|number|false|alpha value
»»» hex|string|false|hex color value
»» visible|boolean|false|toggles layer visibility.
»» pointsize|number|false|defines point size in threejs
»» linewidth|number|false|defines line thickness in threejs
»» shininess|number|false|says it all. speckle is superficial.
»» smooth|boolean|false|smooth shading toggle
»» showEdges|boolean|false|display edges or not yo.
»» wireframe|boolean|false|i'm bored.
» properties|Unknown|false|No description
» description|Unknown|false|No description
» x-old-ref|Unknown|false|No description
children|[string]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## SpeckleLayer

<a name="schemaspecklelayer"></a>

```json
{
  "name": "string",
  "guid": "string",
  "orderIndex": 0,
  "startIndex": 0,
  "objectCount": 0,
  "topology": "0;0;0;0-2 0;0;0;1-2",
  "properties": {
    "color": {
      "a": 1,
      "hex": "#d4d4d4"
    },
    "visible": true,
    "pointsize": 0,
    "linewidth": 0,
    "shininess": 0,
    "smooth": true,
    "showEdges": true,
    "wireframe": true
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|Layer's name
guid|string|false|Layer's guid (must be unique)
orderIndex|integer|false|Describes this layer's position in the list of layers.
startIndex|number|false|The index of the first object relative to the stream's objects array
objectCount|number|false|How many objects does this layer have.
topology|string|false|String describing the nested tree structure (Gh centric).
properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
» color|object|false|No description
»» a|number|false|alpha value
»» hex|string|false|hex color value
» visible|boolean|false|toggles layer visibility.
» pointsize|number|false|defines point size in threejs
» linewidth|number|false|defines line thickness in threejs
» shininess|number|false|says it all. speckle is superficial.
» smooth|boolean|false|smooth shading toggle
» showEdges|boolean|false|display edges or not yo.
» wireframe|boolean|false|i'm bored.
type|Unknown|false|No description
properties|Unknown|false|No description
description|Unknown|false|No description
x-old-ref|Unknown|false|No description



## SpeckleLayerProperties

<a name="schemaspecklelayerproperties"></a>

```json
{
  "color": {
    "a": 1,
    "hex": "#d4d4d4"
  },
  "visible": true,
  "pointsize": 0,
  "linewidth": 0,
  "shininess": 0,
  "smooth": true,
  "showEdges": true,
  "wireframe": true
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
color|object|false|No description
» a|number|false|alpha value
» hex|string|false|hex color value
visible|boolean|false|toggles layer visibility.
pointsize|number|false|defines point size in threejs
linewidth|number|false|defines line thickness in threejs
shininess|number|false|says it all. speckle is superficial.
smooth|boolean|false|smooth shading toggle
showEdges|boolean|false|display edges or not yo.
wireframe|boolean|false|i'm bored.



## SpeckleObject

<a name="schemaspeckleobject"></a>

```json
{
  "type": "Boolean",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {}
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|true|object's type
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
type|Unknown|false|No description
description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|Boolean|
type|Number|
type|String|
type|Interval|
type|Interval2d|
type|Point|
type|Vector|
type|Plane|
type|Line|
type|Rectangle|
type|Circle|
type|Box|
type|Polyline|
type|Curve|
type|Mesh|
type|Brep|
type|Null|


## SpeckleBoolean

<a name="schemaspeckleboolean"></a>

```json
{
  "type": "Boolean",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": true
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
value|boolean|false|No description
type|Unknown|false|No description
description|Unknown|false|No description



## SpeckleNumber

<a name="schemaspecklenumber"></a>

```json
{
  "type": "Number",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
value|number|false|A number. Can be float, double, etc.
type|Unknown|false|No description
description|Unknown|false|No description



## SpeckleString

<a name="schemaspecklestring"></a>

```json
{
  "type": "String",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
value|string|false|A string.
type|Unknown|false|No description
description|Unknown|false|No description



## SpeckleInterval

<a name="schemaspeckleinterval"></a>

```json
{
  "type": "Interval",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "start": 0,
  "end": 0
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
start|number|false|No description
end|number|false|No description
type|Unknown|false|No description
description|Unknown|false|No description



## SpeckleInterval2d

<a name="schemaspeckleinterval2d"></a>

```json
{
  "type": "Boolean",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "U": {
    "type": "Interval",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "start": 0,
    "end": 0
  },
  "V": {
    "type": "Interval",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "start": 0,
    "end": 0
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|string|true|object's type
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
U|[SpeckleInterval](#schemaspeckleinterval)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» start|number|false|No description
» end|number|false|No description
» type|Unknown|false|No description
» description|Unknown|false|No description
V|[SpeckleInterval](#schemaspeckleinterval)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» start|number|false|No description
» end|number|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
type|Boolean|
type|Number|
type|String|
type|Interval|
type|Interval2d|
type|Point|
type|Vector|
type|Plane|
type|Line|
type|Rectangle|
type|Circle|
type|Box|
type|Polyline|
type|Curve|
type|Mesh|
type|Brep|
type|Null|


## SpecklePoint

<a name="schemaspecklepoint"></a>

```json
{
  "type": "Point",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
type|Unknown|false|No description
description|Unknown|false|No description
value|[number]|false|No description



## SpeckleVector

<a name="schemaspecklevector"></a>

```json
{
  "type": "Vector",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
type|Unknown|false|No description
description|Unknown|false|No description
value|[number]|false|No description



## SpecklePlane

<a name="schemaspeckleplane"></a>

```json
{
  "type": "Plane",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "Origin": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "Normal": {
    "type": "Vector",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "Xdir": {
    "type": "Vector",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "Ydir": {
    "type": "Vector",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
Origin|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» value|[number]|false|No description
Normal|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description
Xdir|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description
Ydir|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description



## SpeckleLine

<a name="schemaspeckleline"></a>

```json
{
  "type": "Line",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "start": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "end": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
start|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» value|[number]|false|No description
end|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description



## SpeckleRectangle

<a name="schemaspecklerectangle"></a>

```json
{
  "type": "Rectangle",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "A": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "B": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "C": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "D": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
A|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» value|[number]|false|No description
B|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description
C|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description
D|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description



## SpeckleCircle

<a name="schemaspecklecircle"></a>

```json
{
  "type": "Circle",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "radius": 0,
  "center": {
    "type": "Point",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  },
  "normal": {
    "type": "Vector",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
radius|number|false|No description
center|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» value|[number]|false|No description
normal|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» value|[number]|false|No description



## SpeckleBox

<a name="schemaspecklebox"></a>

```json
{
  "type": "Box",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "basePlane": {
    "type": "Plane",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "Origin": {
      "type": "Point",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "value": [
        0
      ]
    },
    "Normal": {
      "type": "Vector",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "value": [
        0
      ]
    },
    "Xdir": {
      "type": "Vector",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "value": [
        0
      ]
    },
    "Ydir": {
      "type": "Vector",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "value": [
        0
      ]
    }
  },
  "xSize": {
    "type": "Interval",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "start": 0,
    "end": 0
  },
  "ySize": {
    "type": "Interval",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "start": 0,
    "end": 0
  },
  "zSize": {
    "type": "Interval",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "start": 0,
    "end": 0
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
basePlane|[SpecklePlane](#schemaspeckleplane)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» Origin|[SpecklePoint](#schemaspecklepoint)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|Unknown|true|No description
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» type|Unknown|false|No description
»» description|Unknown|false|No description
»» value|[number]|false|No description
» Normal|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|Unknown|true|No description
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» value|[number]|false|No description
» Xdir|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|Unknown|true|No description
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» value|[number]|false|No description
» Ydir|[SpeckleVector](#schemaspecklevector)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|Unknown|true|No description
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» value|[number]|false|No description
xSize|[SpeckleInterval](#schemaspeckleinterval)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» start|number|false|No description
» end|number|false|No description
ySize|[SpeckleInterval](#schemaspeckleinterval)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» start|number|false|No description
» end|number|false|No description
zSize|[SpeckleInterval](#schemaspeckleinterval)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» start|number|false|No description
» end|number|false|No description



## SpecklePolyline

<a name="schemaspecklepolyline"></a>

```json
{
  "type": "Polyline",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "value": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
type|Unknown|false|No description
description|Unknown|false|No description
value|[number]|false|No description



## SpeckleCurve

<a name="schemaspecklecurve"></a>

```json
{
  "type": "Curve",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "base64": "string",
  "provenance": "string",
  "displayValue": {
    "type": "Polyline",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "value": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
base64|string|false|See SpeckleBrep.
provenance|string|false|See SpeckleBrep.
displayValue|[SpecklePolyline](#schemaspecklepolyline)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» value|[number]|false|No description



## SpeckleMesh

<a name="schemaspecklemesh"></a>

```json
{
  "type": "Mesh",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "vertices": [
    0
  ],
  "faces": [
    0
  ],
  "colors": [
    0
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
type|Unknown|false|No description
description|Unknown|false|No description
vertices|[number]|false|No description
faces|[number]|false|No description
colors|[number]|false|No description



## SpeckleBrep

<a name="schemaspecklebrep"></a>

```json
{
  "type": "Brep",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "base64": "string",
  "provenance": "string",
  "displayValue": {
    "type": "Mesh",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "vertices": [
      0
    ],
    "faces": [
      0
    ],
    "colors": [
      0
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
type|Unknown|true|No description
hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
properties|object|false|Anything goes in here, including other (speckle) objects.
base64|string|false|A base64 encoded string of the raw byte array of the object. Do not worry base64 encoding making strings 1.5x bigger, gzip essentially neutralises this - both in transit and in the db.
provenance|string|false|A short prefix of where the base64 comes from. For example, Rhino objects get ON aka Open Nurbs. Later down the road this should be a strict enum.
displayValue|[SpeckleMesh](#schemaspecklemesh)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|Unknown|true|No description
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
» vertices|[number]|false|No description
» faces|[number]|false|No description
» colors|[number]|false|No description



## PayloadAccountRegister

<a name="schemapayloadaccountregister"></a>

```json
{
  "email": "string",
  "password": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
email|string|true|No description
password|string|true|No description
name|string|false|No description
surname|string|false|No description
company|string|false|No description



## PayloadAccountLogin

<a name="schemapayloadaccountlogin"></a>

```json
{
  "email": "string",
  "password": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
email|string|true|No description
password|string|true|No description



## PayloadAccountUpdate

<a name="schemapayloadaccountupdate"></a>

```json
{
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
email|string|false|No description
name|string|false|No description
surname|string|false|No description
company|string|false|No description



## PayloadClientCreate

<a name="schemapayloadclientcreate"></a>

```json
{
  "client": {
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string"
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
client|object|false|No description
» role|string|false|No description
» documentGuid|string|false|No description
» documentName|string|false|No description
» documentType|string|false|No description
» streamId|string|false|No description



## PayloadClientUpdate

<a name="schemapayloadclientupdate"></a>

```json
{
  "client": {
    "_id": "string",
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string",
    "owner": "string",
    "online": true
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
client|[SpeckleClient](#schemaspeckleclient)|false|A representation of the manifestation of a Speckle Client. Whenever an instance of a client is born in any software, it should get its matching identity on the server. When deserialising itself, it should call back to the database and set itself as online. Its uuid sould server as sessionId for the websocket client.
» _id|string|false|Database uuid.
» role|string|false|Sender, Receiver, Mixed (for both), Parametric Sender if it can operate on parameters inside a defintion, or whatever else we can think of.
» documentGuid|string|false|No description
» documentName|string|false|No description
» documentType|string|false|No description
» streamId|string|false|The streamId that this clients 'listens to'.
» owner|string|false|No description
» online|boolean|false|Is it accessible from the server or not?



## PayloadStreamUpdate

<a name="schemapayloadstreamupdate"></a>

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ],
  "name": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|false|No description
objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description
layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
» name|string|false|Layer's name
» guid|string|false|Layer's guid (must be unique)
» orderIndex|integer|false|Describes this layer's position in the list of layers.
» startIndex|number|false|The index of the first object relative to the stream's objects array
» objectCount|number|false|How many objects does this layer have.
» topology|string|false|String describing the nested tree structure (Gh centric).
» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»» color|object|false|No description
»»» a|number|false|alpha value
»»» hex|string|false|hex color value
»» visible|boolean|false|toggles layer visibility.
»» pointsize|number|false|defines point size in threejs
»» linewidth|number|false|defines line thickness in threejs
»» shininess|number|false|says it all. speckle is superficial.
»» smooth|boolean|false|smooth shading toggle
»» showEdges|boolean|false|display edges or not yo.
»» wireframe|boolean|false|i'm bored.
» properties|Unknown|false|No description
» description|Unknown|false|No description
» x-old-ref|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## PayloadStreamNameUpdate

<a name="schemapayloadstreamnameupdate"></a>

```json
{
  "name": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
name|string|true|No description



## PayloadCreateObject

<a name="schemapayloadcreateobject"></a>

```json
{
  "object": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
object|[SpeckleObject](#schemaspeckleobject)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## PayloadObjectUpdate

<a name="schemapayloadobjectupdate"></a>

```json
{
  "object": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
object|[SpeckleObject](#schemaspeckleobject)|true|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## PayloadObjectCreateWithArray

<a name="schemapayloadobjectcreatewitharray"></a>

```json
{
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## PayloadObjectGetWithArray

<a name="schemapayloadobjectgetwitharray"></a>

```json
{
  "objects": [
    "string"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
objects|[string]|false|No description



## ResponseBase

<a name="schemaresponsebase"></a>

```json
{
  "success": true,
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.



## ResponseAccountRegister

<a name="schemaresponseaccountregister"></a>

```json
{
  "success": true,
  "message": "string",
  "token": "string",
  "apiToken": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
token|string|false|Session token, expires in 1 day.
apiToken|string|false|API token, expires in 1 year.



## ResponseAccountLogin

<a name="schemaresponseaccountlogin"></a>

```json
{
  "success": true,
  "message": "string",
  "token": "string",
  "apiToken": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
token|string|false|Session token, expires in 1 day.
apiToken|string|false|API token, expires in 1 year.



## ResponseAccountStreams

<a name="schemaresponseaccountstreams"></a>

```json
{
  "success": true,
  "message": "string",
  "streams": [
    {
      "_id": "string",
      "streamId": "string",
      "owner": "string",
      "private": false,
      "name": "Anonymous Stream",
      "objects": [
        {
          "type": "Boolean",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {}
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "0;0;0;0-2 0;0;0;1-2",
          "properties": {
            "color": {
              "a": 1,
              "hex": "#d4d4d4"
            },
            "visible": true,
            "pointsize": 0,
            "linewidth": 0,
            "shininess": 0,
            "smooth": true,
            "showEdges": true,
            "wireframe": true
          }
        }
      ],
      "parent": "string",
      "children": [
        "string"
      ]
    }
  ],
  "sharedStreams": [
    {
      "_id": "string",
      "streamId": "string",
      "owner": "string",
      "private": false,
      "name": "Anonymous Stream",
      "objects": [
        {
          "type": "Boolean",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {}
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "0;0;0;0-2 0;0;0;1-2",
          "properties": {
            "color": {
              "a": 1,
              "hex": "#d4d4d4"
            },
            "visible": true,
            "pointsize": 0,
            "linewidth": 0,
            "shininess": 0,
            "smooth": true,
            "showEdges": true,
            "wireframe": true
          }
        }
      ],
      "parent": "string",
      "children": [
        "string"
      ]
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
streams|[[DataStream](#schemadatastream)]|false|Describes a data stream. The data stream's `streamId` will define the channel on which real-time updates will be distributed on the websocket server.
» _id|string|false|Database uuid.
» streamId|string|true|The stream's short id.
» owner|string|false|The owner's user id.
» private|boolean|false|No description
» name|string|true|The data stream's name
» parent|string|false|Parent stream's id, if any. If null, this is a `root` stream.
» objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|string|true|object's type
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» type|Unknown|false|No description
»» description|Unknown|false|No description
» layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description
»» description|Unknown|false|No description
»» x-old-ref|Unknown|false|No description
» children|[string]|false|No description
sharedStreams|[[DataStream](#schemadatastream)]|false|Describes a data stream. The data stream's `streamId` will define the channel on which real-time updates will be distributed on the websocket server.
» _id|string|false|Database uuid.
» streamId|string|true|The stream's short id.
» owner|string|false|The owner's user id.
» private|boolean|false|No description
» name|string|true|The data stream's name
» parent|string|false|Parent stream's id, if any. If null, this is a `root` stream.
» objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|string|true|object's type
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
» layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description
» children|[string]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|


## ResponseAccountClients

<a name="schemaresponseaccountclients"></a>

```json
{
  "success": true,
  "message": "string",
  "clients": [
    {
      "_id": "string",
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "streamId": "string",
      "owner": "string",
      "online": true
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
clients|[[SpeckleClient](#schemaspeckleclient)]|false|A representation of the manifestation of a Speckle Client. Whenever an instance of a client is born in any software, it should get its matching identity on the server. When deserialising itself, it should call back to the database and set itself as online. Its uuid sould server as sessionId for the websocket client.
» _id|string|false|Database uuid.
» role|string|false|Sender, Receiver, Mixed (for both), Parametric Sender if it can operate on parameters inside a defintion, or whatever else we can think of.
» documentGuid|string|false|No description
» documentName|string|false|No description
» documentType|string|false|No description
» streamId|string|false|The streamId that this clients 'listens to'.
» owner|string|false|No description
» online|boolean|false|Is it accessible from the server or not?



## ResponseAccountProfile

<a name="schemaresponseaccountprofile"></a>

```json
{
  "success": true,
  "message": "string",
  "user": {
    "_id": "string",
    "apitoken": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
user|[User](#schemauser)|false|Describes a user.
» _id|string|false|Database uuid.
» apitoken|string|false|a signed jwt token that expires in 1 year.
» email|string|false|user's email
» name|string|false|User's given name
» surname|string|false|User's family name
» company|string|false|Users's company
» logins|[object]|false|it's a timestamp XD
»» date|string|false|No description



## ResponseClientCreate

<a name="schemaresponseclientcreate"></a>

```json
{
  "success": true,
  "message": "string",
  "clientId": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
clientId|string|false|the client's uuid. save & serialise this!



## ResponseClientGet

<a name="schemaresponseclientget"></a>

```json
{
  "success": true,
  "message": "string",
  "client": {
    "_id": "string",
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "streamId": "string",
    "owner": "string",
    "online": true
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
client|[SpeckleClient](#schemaspeckleclient)|false|A representation of the manifestation of a Speckle Client. Whenever an instance of a client is born in any software, it should get its matching identity on the server. When deserialising itself, it should call back to the database and set itself as online. Its uuid sould server as sessionId for the websocket client.
» _id|string|false|Database uuid.
» role|string|false|Sender, Receiver, Mixed (for both), Parametric Sender if it can operate on parameters inside a defintion, or whatever else we can think of.
» documentGuid|string|false|No description
» documentName|string|false|No description
» documentType|string|false|No description
» streamId|string|false|The streamId that this clients 'listens to'.
» owner|string|false|No description
» online|boolean|false|Is it accessible from the server or not?



## ResponseStreamCreate

<a name="schemaresponsestreamcreate"></a>

```json
{
  "success": true,
  "message": "string",
  "stream": {
    "_id": "string",
    "streamId": "string",
    "owner": "string",
    "private": false,
    "name": "Anonymous Stream",
    "objects": [
      {
        "type": "Boolean",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {}
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "parent": "string",
    "children": [
      "string"
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
stream|[DataStream](#schemadatastream)|false|Describes a data stream. The data stream's `streamId` will define the channel on which real-time updates will be distributed on the websocket server.
» _id|string|false|Database uuid.
» streamId|string|true|The stream's short id.
» owner|string|false|The owner's user id.
» private|boolean|false|No description
» name|string|true|The data stream's name
» parent|string|false|Parent stream's id, if any. If null, this is a `root` stream.
» objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|string|true|object's type
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» type|Unknown|false|No description
»» description|Unknown|false|No description
» layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description
»» description|Unknown|false|No description
»» x-old-ref|Unknown|false|No description
» children|[string]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|


## ResponseStreamGet

<a name="schemaresponsestreamget"></a>

```json
{
  "success": true,
  "message": "string",
  "stream": {
    "_id": "string",
    "streamId": "string",
    "owner": "string",
    "private": false,
    "name": "Anonymous Stream",
    "objects": [
      {
        "type": "Boolean",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {}
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "parent": "string",
    "children": [
      "string"
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
stream|[DataStream](#schemadatastream)|false|Describes a data stream. The data stream's `streamId` will define the channel on which real-time updates will be distributed on the websocket server.
» _id|string|false|Database uuid.
» streamId|string|true|The stream's short id.
» owner|string|false|The owner's user id.
» private|boolean|false|No description
» name|string|true|The data stream's name
» parent|string|false|Parent stream's id, if any. If null, this is a `root` stream.
» objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
»» type|string|true|object's type
»» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
»» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
»» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
»» properties|object|false|Anything goes in here, including other (speckle) objects.
»» type|Unknown|false|No description
»» description|Unknown|false|No description
» layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description
»» description|Unknown|false|No description
»» x-old-ref|Unknown|false|No description
» children|[string]|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
»» type|Boolean|
»» type|Number|
»» type|String|
»» type|Interval|
»» type|Interval2d|
»» type|Point|
»» type|Vector|
»» type|Plane|
»» type|Line|
»» type|Rectangle|
»» type|Circle|
»» type|Box|
»» type|Polyline|
»» type|Curve|
»» type|Mesh|
»» type|Brep|
»» type|Null|


## ResponseStreamLayersGet

<a name="schemaresponsestreamlayersget"></a>

```json
{
  "success": true,
  "message": "string",
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "0;0;0;0-2 0;0;0;1-2",
      "properties": {
        "color": {
          "a": 1,
          "hex": "#d4d4d4"
        },
        "visible": true,
        "pointsize": 0,
        "linewidth": 0,
        "shininess": 0,
        "smooth": true,
        "showEdges": true,
        "wireframe": true
      }
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
layers|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
» name|string|false|Layer's name
» guid|string|false|Layer's guid (must be unique)
» orderIndex|integer|false|Describes this layer's position in the list of layers.
» startIndex|number|false|The index of the first object relative to the stream's objects array
» objectCount|number|false|How many objects does this layer have.
» topology|string|false|String describing the nested tree structure (Gh centric).
» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»» color|object|false|No description
»»» a|number|false|alpha value
»»» hex|string|false|hex color value
»» visible|boolean|false|toggles layer visibility.
»» pointsize|number|false|defines point size in threejs
»» linewidth|number|false|defines line thickness in threejs
»» shininess|number|false|says it all. speckle is superficial.
»» smooth|boolean|false|smooth shading toggle
»» showEdges|boolean|false|display edges or not yo.
»» wireframe|boolean|false|i'm bored.
» type|Unknown|false|No description
» properties|Unknown|false|No description
» description|Unknown|false|No description
» x-old-ref|Unknown|false|No description



## ResponseStreamNameGet

<a name="schemaresponsestreamnameget"></a>

```json
{
  "success": true,
  "message": "string",
  "name": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
name|string|false|No description



## ResponseStreamUpdate

<a name="schemaresponsestreamupdate"></a>

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
objects|[string]|false|No description



## ResponseStreamClone

<a name="schemaresponsestreamclone"></a>

```json
{
  "success": true,
  "message": "string",
  "clone": {
    "_id": "string",
    "streamId": "string"
  },
  "parent": {
    "_id": "string",
    "streamId": "string",
    "children": [
      "string"
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
clone|object|false|No description
» _id|string|false|the cloned data stream's new id.
» streamId|string|false|the cloned data stream's new streamId.
parent|object|false|No description
» _id|string|false|No description
» streamId|string|false|No description
» children|[string]|false|No description



## ResponseStreamDiff

<a name="schemaresponsestreamdiff"></a>

```json
{
  "success": true,
  "message": "string",
  "objects": {
    "common": [
      "string"
    ],
    "inA": [
      "string"
    ],
    "inB": [
      "string"
    ]
  },
  "layers": {
    "common": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "inA": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ],
    "inB": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "0;0;0;0-2 0;0;0;1-2",
        "properties": {
          "color": {
            "a": 1,
            "hex": "#d4d4d4"
          },
          "visible": true,
          "pointsize": 0,
          "linewidth": 0,
          "shininess": 0,
          "smooth": true,
          "showEdges": true,
          "wireframe": true
        }
      }
    ]
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
objects|object|false|No description
» common|[string]|false|No description
» inA|[string]|false|No description
» inB|[string]|false|No description
layers|object|false|No description
» common|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» type|Unknown|false|No description
»» properties|Unknown|false|No description
»» description|Unknown|false|No description
»» x-old-ref|Unknown|false|No description
» inA|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description
» inB|[[SpeckleLayer](#schemaspecklelayer)]|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
»» name|string|false|Layer's name
»» guid|string|false|Layer's guid (must be unique)
»» orderIndex|integer|false|Describes this layer's position in the list of layers.
»» startIndex|number|false|The index of the first object relative to the stream's objects array
»» objectCount|number|false|How many objects does this layer have.
»» topology|string|false|String describing the nested tree structure (Gh centric).
»» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»»» color|object|false|No description
»»»» a|number|false|alpha value
»»»» hex|string|false|hex color value
»»» visible|boolean|false|toggles layer visibility.
»»» pointsize|number|false|defines point size in threejs
»»» linewidth|number|false|defines line thickness in threejs
»»» shininess|number|false|says it all. speckle is superficial.
»»» smooth|boolean|false|smooth shading toggle
»»» showEdges|boolean|false|display edges or not yo.
»»» wireframe|boolean|false|i'm bored.
»» properties|Unknown|false|No description



## ResponseSingleLayer

<a name="schemaresponsesinglelayer"></a>

```json
{
  "success": true,
  "message": "string",
  "layer": {
    "name": "string",
    "guid": "string",
    "orderIndex": 0,
    "startIndex": 0,
    "objectCount": 0,
    "topology": "0;0;0;0-2 0;0;0;1-2",
    "properties": {
      "color": {
        "a": 1,
        "hex": "#d4d4d4"
      },
      "visible": true,
      "pointsize": 0,
      "linewidth": 0,
      "shininess": 0,
      "smooth": true,
      "showEdges": true,
      "wireframe": true
    }
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
layer|[SpeckleLayer](#schemaspecklelayer)|false|Describes a speckle layer. To assign objects to a speckle layer, you'll need to start at `objects[ layer.startIndex ]` and finish at `objects[ layer.startIndex + layer.objectCount ]`.
» name|string|false|Layer's name
» guid|string|false|Layer's guid (must be unique)
» orderIndex|integer|false|Describes this layer's position in the list of layers.
» startIndex|number|false|The index of the first object relative to the stream's objects array
» objectCount|number|false|How many objects does this layer have.
» topology|string|false|String describing the nested tree structure (Gh centric).
» properties|[SpeckleLayerProperties](#schemaspecklelayerproperties)|false|Holds stream layer properties, mostly for displaying purposes. This object will be filled up with garbage from threejs and others, but below is a minimal schema.
»» color|object|false|No description
»»» a|number|false|alpha value
»»» hex|string|false|hex color value
»» visible|boolean|false|toggles layer visibility.
»» pointsize|number|false|defines point size in threejs
»» linewidth|number|false|defines line thickness in threejs
»» shininess|number|false|says it all. speckle is superficial.
»» smooth|boolean|false|smooth shading toggle
»» showEdges|boolean|false|display edges or not yo.
»» wireframe|boolean|false|i'm bored.
» type|Unknown|false|No description
» properties|Unknown|false|No description
» description|Unknown|false|No description
» x-old-ref|Unknown|false|No description



## ResponseObjectCreate

<a name="schemaresponseobjectcreate"></a>

```json
{
  "success": true,
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.



## ResponseObjectGet

<a name="schemaresponseobjectget"></a>

```json
{
  "success": true,
  "message": "string",
  "speckleObject": {
    "type": "Boolean",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {}
  }
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
speckleObject|[SpeckleObject](#schemaspeckleobject)|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## ResponseObjectUpdate

<a name="schemaresponseobjectupdate"></a>

```json
{
  "success": true,
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.



## ResponseObjectWithArrayCreate

<a name="schemaresponseobjectwitharraycreate"></a>

```json
{
  "success": true,
  "message": "string"
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.



## ResponseGetObjects

<a name="schemaresponsegetobjects"></a>

```json
{
  "success": true,
  "message": "string",
  "objects": [
    {
      "type": "Boolean",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {}
    }
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
objects|[[SpeckleObject](#schemaspeckleobject)]|false|Base class that is inherited by all other Speckle objects. The only required value is its `type`.  Important note: the following types: `[ Polyline, Curve, Mesh, Brep ]` are treated server side in a special manner, as they can be unbounded in size.
» type|string|true|object's type
» hash|string|false|Object's unique hash. It's generated server-side from JSON.stringify( obj.properties ) + obj.geometryHash using a murmurhash3 128bit function.
» geometryHash|string|false|If the object contains 'heavy' geometry, it should have a geometry hash.
» applicationId|string|false|If this object is not an ephemeral object, (ie coming from Grasshopper or Dynamo), and has a unique, persistent and consistent application id, this is where to store said guid.
» properties|object|false|Anything goes in here, including other (speckle) objects.
» type|Unknown|false|No description
» description|Unknown|false|No description


#### Enumerated Values

|Property|Value|
|---|---|
» type|Boolean|
» type|Number|
» type|String|
» type|Interval|
» type|Interval2d|
» type|Point|
» type|Vector|
» type|Plane|
» type|Line|
» type|Rectangle|
» type|Circle|
» type|Box|
» type|Polyline|
» type|Curve|
» type|Mesh|
» type|Brep|
» type|Null|


## ResponsePostObjects

<a name="schemaresponsepostobjects"></a>

```json
{
  "success": true,
  "message": "string",
  "objects": [
    "string"
  ]
} 
```

### Properties

Name|Type|Required|Description
---|---|---|---|
success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.
message|string|false|Either an error or a confirmation.
objects|[string]|false|No description





