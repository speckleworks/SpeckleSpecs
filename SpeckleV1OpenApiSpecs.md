---
title: Speckle OpenApi Specs v1.0.0-beta
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

# Speckle OpenApi Specs v1.0.0-beta

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Documentation & specifications for the Speckle Server & Speckle Objects.

Base URLs:

* <a href="http://localhost:3000/api/v1">http://localhost:3000/api/v1</a>

* <a href="https://localhost:3000/api/v1">https://localhost:3000/api/v1</a>



Email: <a href="mailto:hello@speckle.works">SpeckleWorks</a> Web: <a href="https://speckle.works">SpeckleWorks</a> 

# Authentication


* API Key
    - Parameter Name: **Authorization**, in: header. 



# Accounts

Register, Login and more.

## UserRegister

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/accounts/register \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/accounts/register HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts/register',
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string",
  "logins": [
    {
      "date": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/accounts/register',
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

result = RestClient.post 'http://localhost:3000/api/v1/accounts/register',
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

r = requests.post('http://localhost:3000/api/v1/accounts/register', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts/register");
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
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
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[User](#schemauser)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "role": "string",
    "avatar": "string",
    "apitoken": "string",
    "token": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  },
  "resources": [
    {
      "_id": "string",
      "role": "string",
      "avatar": "string",
      "apitoken": "string",
      "token": "string",
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
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed to register a new user.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserLogin

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/accounts/login \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/accounts/login HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts/login',
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string",
  "logins": [
    {
      "date": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/accounts/login',
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

result = RestClient.post 'http://localhost:3000/api/v1/accounts/login',
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

r = requests.post('http://localhost:3000/api/v1/accounts/login', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts/login");
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
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
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[User](#schemauser)|true|The only required elements are email and password.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "role": "string",
    "avatar": "string",
    "apitoken": "string",
    "token": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  },
  "resources": [
    {
      "_id": "string",
      "role": "string",
      "avatar": "string",
      "apitoken": "string",
      "token": "string",
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
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|You've logged in.|[ResponseUser](#schemaresponseuser)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserSearch

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/accounts/search \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/accounts/search HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts/search',
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string",
  "logins": [
    {
      "date": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/accounts/search',
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

result = RestClient.post 'http://localhost:3000/api/v1/accounts/search',
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

r = requests.post('http://localhost:3000/api/v1/accounts/search', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts/search");
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

`POST /accounts/search`

*UserSearch*

Search for a user by a (partial) email address.

> Body parameter

```json
{
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
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
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[User](#schemauser)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "role": "string",
    "avatar": "string",
    "apitoken": "string",
    "token": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  },
  "resources": [
    {
      "_id": "string",
      "role": "string",
      "avatar": "string",
      "apitoken": "string",
      "token": "string",
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
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/accounts \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/accounts HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts',
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

fetch('http://localhost:3000/api/v1/accounts',
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

result = RestClient.get 'http://localhost:3000/api/v1/accounts',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts");
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

`GET /accounts`

*UserGet*

Gets your profile.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "role": "string",
    "avatar": "string",
    "apitoken": "string",
    "token": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  },
  "resources": [
    {
      "_id": "string",
      "role": "string",
      "avatar": "string",
      "apitoken": "string",
      "token": "string",
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
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserUpdateProfile

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/accounts \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/accounts HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts',
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
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
  "email": "string",
  "name": "string",
  "surname": "string",
  "company": "string",
  "logins": [
    {
      "date": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/accounts',
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

result = RestClient.put 'http://localhost:3000/api/v1/accounts',
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

r = requests.put('http://localhost:3000/api/v1/accounts', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts");
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

`PUT /accounts`

*UserUpdateProfile*

Updates your profile.

> Body parameter

```json
{
  "_id": "string",
  "role": "string",
  "avatar": "string",
  "apitoken": "string",
  "token": "string",
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
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[User](#schemauser)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Things are looking good yo.|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## UserGetProfileById

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/accounts/{userId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/accounts/{userId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/accounts/{userId}',
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

fetch('http://localhost:3000/api/v1/accounts/{userId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/accounts/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/accounts/{userId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/accounts/{userId}");
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

`GET /accounts/{userId}`

*UserGetProfileById*

Gets a user's profile.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
userId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "role": "string",
    "avatar": "string",
    "apitoken": "string",
    "token": "string",
    "email": "string",
    "name": "string",
    "surname": "string",
    "company": "string",
    "logins": [
      {
        "date": "string"
      }
    ]
  },
  "resources": [
    {
      "_id": "string",
      "role": "string",
      "avatar": "string",
      "apitoken": "string",
      "token": "string",
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
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Clients

Create, get and update application clients.

## ClientGetAll

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/clients \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/clients HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/clients',
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

fetch('http://localhost:3000/api/v1/clients',
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

result = RestClient.get 'http://localhost:3000/api/v1/clients',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/clients', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/clients");
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

`GET /clients`

*ClientGetAll*

Gets a user's profile.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "documentLocation": "string",
    "streamId": "string",
    "online": true
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "documentLocation": "string",
      "streamId": "string",
      "online": true
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/clients \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/clients HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/clients',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "role": "string",
  "documentGuid": "string",
  "documentName": "string",
  "documentType": "string",
  "documentLocation": "string",
  "streamId": "string",
  "online": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/clients',
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

result = RestClient.post 'http://localhost:3000/api/v1/clients',
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

r = requests.post('http://localhost:3000/api/v1/clients', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/clients");
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

Create a client

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "role": "string",
  "documentGuid": "string",
  "documentName": "string",
  "documentType": "string",
  "documentLocation": "string",
  "streamId": "string",
  "online": true
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[AppClient](#schemaappclient)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "documentLocation": "string",
    "streamId": "string",
    "online": true
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "documentLocation": "string",
      "streamId": "string",
      "online": true
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/clients/{clientId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/clients/{clientId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/clients/{clientId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "role": "string",
  "documentGuid": "string",
  "documentName": "string",
  "documentType": "string",
  "documentLocation": "string",
  "streamId": "string",
  "online": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/clients/{clientId}',
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

result = RestClient.put 'http://localhost:3000/api/v1/clients/{clientId}',
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

r = requests.put('http://localhost:3000/api/v1/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/clients/{clientId}");
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

Update a client

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "role": "string",
  "documentGuid": "string",
  "documentName": "string",
  "documentType": "string",
  "documentLocation": "string",
  "streamId": "string",
  "online": true
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|No description
body|body|[AppClient](#schemaappclient)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "documentLocation": "string",
    "streamId": "string",
    "online": true
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "documentLocation": "string",
      "streamId": "string",
      "online": true
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/clients/{clientId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/clients/{clientId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/clients/{clientId}',
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

fetch('http://localhost:3000/api/v1/clients/{clientId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/clients/{clientId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/clients/{clientId}");
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

Get a client

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "role": "string",
    "documentGuid": "string",
    "documentName": "string",
    "documentType": "string",
    "documentLocation": "string",
    "streamId": "string",
    "online": true
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "role": "string",
      "documentGuid": "string",
      "documentName": "string",
      "documentType": "string",
      "documentLocation": "string",
      "streamId": "string",
      "online": true
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseClient](#schemaresponseclient)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ClientDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/v1/clients/{clientId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/api/v1/clients/{clientId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/clients/{clientId}',
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

fetch('http://localhost:3000/api/v1/clients/{clientId}',
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

result = RestClient.delete 'http://localhost:3000/api/v1/clients/{clientId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/api/v1/clients/{clientId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/clients/{clientId}");
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

Deletes a client

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
clientId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Projects

Create, get and update projects.

## ProjectGetAll

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/projects \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/projects HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/projects',
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

fetch('http://localhost:3000/api/v1/projects',
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

result = RestClient.get 'http://localhost:3000/api/v1/projects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/projects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/projects");
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

`GET /projects`

*ProjectGetAll*

Gets a user's projects.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "name": "string",
    "users": [
      "string"
    ],
    "streams": [
      "string"
    ],
    "subProjects": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "name": "string",
      "users": [
        "string"
      ],
      "streams": [
        "string"
      ],
      "subProjects": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseProject](#schemaresponseproject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ProjectCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/projects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/projects HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/projects',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "name": "string",
  "users": [
    "string"
  ],
  "streams": [
    "string"
  ],
  "subProjects": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/projects',
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

result = RestClient.post 'http://localhost:3000/api/v1/projects',
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

r = requests.post('http://localhost:3000/api/v1/projects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/projects");
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

`POST /projects`

*ProjectCreate*

Create a project

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "name": "string",
  "users": [
    "string"
  ],
  "streams": [
    "string"
  ],
  "subProjects": [
    "string"
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[Project](#schemaproject)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "name": "string",
    "users": [
      "string"
    ],
    "streams": [
      "string"
    ],
    "subProjects": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "name": "string",
      "users": [
        "string"
      ],
      "streams": [
        "string"
      ],
      "subProjects": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseProject](#schemaresponseproject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ProjectUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/projects/{projectId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/projects/{projectId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/projects/{projectId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "name": "string",
  "users": [
    "string"
  ],
  "streams": [
    "string"
  ],
  "subProjects": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/projects/{projectId}',
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

result = RestClient.put 'http://localhost:3000/api/v1/projects/{projectId}',
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

r = requests.put('http://localhost:3000/api/v1/projects/{projectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/projects/{projectId}");
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

`PUT /projects/{projectId}`

*ProjectUpdate*

Update a project

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "name": "string",
  "users": [
    "string"
  ],
  "streams": [
    "string"
  ],
  "subProjects": [
    "string"
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
projectId|path|string|true|No description
body|body|[Project](#schemaproject)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "name": "string",
    "users": [
      "string"
    ],
    "streams": [
      "string"
    ],
    "subProjects": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "name": "string",
      "users": [
        "string"
      ],
      "streams": [
        "string"
      ],
      "subProjects": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseProject](#schemaresponseproject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ProjectGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/projects/{projectId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/projects/{projectId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/projects/{projectId}',
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

fetch('http://localhost:3000/api/v1/projects/{projectId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/projects/{projectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/projects/{projectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/projects/{projectId}");
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

`GET /projects/{projectId}`

*ProjectGet*

Get a project

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
projectId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "name": "string",
    "users": [
      "string"
    ],
    "streams": [
      "string"
    ],
    "subProjects": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "name": "string",
      "users": [
        "string"
      ],
      "streams": [
        "string"
      ],
      "subProjects": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseProject](#schemaresponseproject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ProjectDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/v1/projects/{projectId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/api/v1/projects/{projectId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/projects/{projectId}',
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

fetch('http://localhost:3000/api/v1/projects/{projectId}',
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

result = RestClient.delete 'http://localhost:3000/api/v1/projects/{projectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/api/v1/projects/{projectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/projects/{projectId}");
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

`DELETE /projects/{projectId}`

*ProjectDelete*

Deletes a project

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
projectId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Comments

Create, get and update comments.

## CommentCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/comments/{resourceType}/{resourceId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/comments/{resourceType}/{resourceId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "resource": {
    "resourceType": "string",
    "resourceId": "string"
  },
  "text": "string",
  "assignedTo": [
    "string"
  ],
  "closed": true,
  "labels": [
    "string"
  ],
  "view": {},
  "screenshot": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
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

result = RestClient.post 'http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
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

r = requests.post('http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}");
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

`POST /comments/{resourceType}/{resourceId}`

*CommentCreate*

Creates a comment on a resource.

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "resource": {
    "resourceType": "string",
    "resourceId": "string"
  },
  "text": "string",
  "assignedTo": [
    "string"
  ],
  "closed": true,
  "labels": [
    "string"
  ],
  "view": {},
  "screenshot": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
resourceType|path|string|true|The resource type you want to comment on.
resourceId|path|string|true|The resource id you want to comment on. In the case of streams, it must be a streamId.
body|body|[Comment](#schemacomment)|true|No description


#### Enumerated Values

|Parameter|Value|
|---|---|
resourceType|stream|
resourceType|object|
resourceType|project|
resourceType|comment|

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "resource": {
      "resourceType": "string",
      "resourceId": "string"
    },
    "text": "string",
    "assignedTo": [
      "string"
    ],
    "closed": true,
    "labels": [
      "string"
    ],
    "view": {},
    "screenshot": "string"
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "resource": {
        "resourceType": "string",
        "resourceId": "string"
      },
      "text": "string",
      "assignedTo": [
        "string"
      ],
      "closed": true,
      "labels": [
        "string"
      ],
      "view": {},
      "screenshot": "string"
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## CommentGetFromResource

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/comments/{resourceType}/{resourceId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/comments/{resourceType}/{resourceId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
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

fetch('http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/comments/{resourceType}/{resourceId}");
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

`GET /comments/{resourceType}/{resourceId}`

*CommentGetFromResource*

Gets the comments from a resource.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
resourceType|path|string|true|The resource type you want to comment on.
resourceId|path|string|true|The resource id you want to comment on. In the case of streams, it must be a streamId.


#### Enumerated Values

|Parameter|Value|
|---|---|
resourceType|stream|
resourceType|object|
resourceType|project|
resourceType|comment|

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "resource": {
      "resourceType": "string",
      "resourceId": "string"
    },
    "text": "string",
    "assignedTo": [
      "string"
    ],
    "closed": true,
    "labels": [
      "string"
    ],
    "view": {},
    "screenshot": "string"
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "resource": {
        "resourceType": "string",
        "resourceId": "string"
      },
      "text": "string",
      "assignedTo": [
        "string"
      ],
      "closed": true,
      "labels": [
        "string"
      ],
      "view": {},
      "screenshot": "string"
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## CommentGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/comments/{commentId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/comments/{commentId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/comments/{commentId}',
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

fetch('http://localhost:3000/api/v1/comments/{commentId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/comments/{commentId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/comments/{commentId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/comments/{commentId}");
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

`GET /comments/{commentId}`

*CommentGet*

Gets a specific comment.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
commentId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "resource": {
      "resourceType": "string",
      "resourceId": "string"
    },
    "text": "string",
    "assignedTo": [
      "string"
    ],
    "closed": true,
    "labels": [
      "string"
    ],
    "view": {},
    "screenshot": "string"
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "resource": {
        "resourceType": "string",
        "resourceId": "string"
      },
      "text": "string",
      "assignedTo": [
        "string"
      ],
      "closed": true,
      "labels": [
        "string"
      ],
      "view": {},
      "screenshot": "string"
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## CommentUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/comments/{commentId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/comments/{commentId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/comments/{commentId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "resource": {
    "resourceType": "string",
    "resourceId": "string"
  },
  "text": "string",
  "assignedTo": [
    "string"
  ],
  "closed": true,
  "labels": [
    "string"
  ],
  "view": {},
  "screenshot": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/comments/{commentId}',
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

result = RestClient.put 'http://localhost:3000/api/v1/comments/{commentId}',
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

r = requests.put('http://localhost:3000/api/v1/comments/{commentId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/comments/{commentId}");
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

`PUT /comments/{commentId}`

*CommentUpdate*

Updates a comment.

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "resource": {
    "resourceType": "string",
    "resourceId": "string"
  },
  "text": "string",
  "assignedTo": [
    "string"
  ],
  "closed": true,
  "labels": [
    "string"
  ],
  "view": {},
  "screenshot": "string"
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
commentId|path|string|true|No description
body|body|[Comment](#schemacomment)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## CommentDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/v1/comments/{commentId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/api/v1/comments/{commentId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/comments/{commentId}',
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

fetch('http://localhost:3000/api/v1/comments/{commentId}',
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

result = RestClient.delete 'http://localhost:3000/api/v1/comments/{commentId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/api/v1/comments/{commentId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/comments/{commentId}");
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

`DELETE /comments/{commentId}`

*CommentDelete*

Deletes a specific comment.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
commentId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Streams

Create, get and update streams.

## StreamsGetAll

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/streams \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/streams HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams',
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

fetch('http://localhost:3000/api/v1/streams',
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

result = RestClient.get 'http://localhost:3000/api/v1/streams',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/streams', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams");
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

`GET /streams`

*StreamsGetAll*

Gets a user's streams.

> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "streamId": "string",
    "name": "string",
    "objects": [
      {
        "_id": "string",
        "owner": "string",
        "private": true,
        "anonymousComments": true,
        "canRead": [
          "string"
        ],
        "canWrite": [
          "string"
        ],
        "comments": [
          "string"
        ],
        "deleted": false,
        "type": "Null",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {},
        "parent": "string",
        "children": [
          "string"
        ],
        "ancestors": [
          "string"
        ],
        "transform": [
          0
        ]
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
    "baseProperties": {},
    "globalMeasures": {},
    "isComputedResult": false,
    "viewerLayers": [
      {}
    ],
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "streamId": "string",
      "name": "string",
      "objects": [
        {
          "_id": "string",
          "owner": "string",
          "private": true,
          "anonymousComments": true,
          "canRead": [
            "string"
          ],
          "canWrite": [
            "string"
          ],
          "comments": [
            "string"
          ],
          "deleted": false,
          "type": "Null",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {},
          "parent": "string",
          "children": [
            "string"
          ],
          "ancestors": [
            "string"
          ],
          "transform": [
            0
          ]
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "string",
          "properties": {
            "color": {
              "a": 1,
              "hex": "string"
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
      "baseProperties": {},
      "globalMeasures": {},
      "isComputedResult": false,
      "viewerLayers": [
        {}
      ],
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/streams \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/streams HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "string",
      "properties": {
        "color": {
          "a": 1,
          "hex": "string"
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
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [
    {}
  ],
  "parent": "string",
  "children": [
    "string"
  ],
  "ancestors": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/streams',
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

result = RestClient.post 'http://localhost:3000/api/v1/streams',
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

r = requests.post('http://localhost:3000/api/v1/streams', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams");
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

Create a stream

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "string",
      "properties": {
        "color": {
          "a": 1,
          "hex": "string"
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
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [
    {}
  ],
  "parent": "string",
  "children": [
    "string"
  ],
  "ancestors": [
    "string"
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|[SpeckleStream](#schemaspecklestream)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "streamId": "string",
    "name": "string",
    "objects": [
      {
        "_id": "string",
        "owner": "string",
        "private": true,
        "anonymousComments": true,
        "canRead": [
          "string"
        ],
        "canWrite": [
          "string"
        ],
        "comments": [
          "string"
        ],
        "deleted": false,
        "type": "Null",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {},
        "parent": "string",
        "children": [
          "string"
        ],
        "ancestors": [
          "string"
        ],
        "transform": [
          0
        ]
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
    "baseProperties": {},
    "globalMeasures": {},
    "isComputedResult": false,
    "viewerLayers": [
      {}
    ],
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "streamId": "string",
      "name": "string",
      "objects": [
        {
          "_id": "string",
          "owner": "string",
          "private": true,
          "anonymousComments": true,
          "canRead": [
            "string"
          ],
          "canWrite": [
            "string"
          ],
          "comments": [
            "string"
          ],
          "deleted": false,
          "type": "Null",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {},
          "parent": "string",
          "children": [
            "string"
          ],
          "ancestors": [
            "string"
          ],
          "transform": [
            0
          ]
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "string",
          "properties": {
            "color": {
              "a": 1,
              "hex": "string"
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
      "baseProperties": {},
      "globalMeasures": {},
      "isComputedResult": false,
      "viewerLayers": [
        {}
      ],
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/streams/{streamId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/streams/{streamId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}',
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

fetch('http://localhost:3000/api/v1/streams/{streamId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/streams/{streamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}");
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

Gets a specific stream.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
query|query|string|false|Specifiy which fields to retrieve, ie `?fields=layers,baseProperties`.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "streamId": "string",
    "name": "string",
    "objects": [
      {
        "_id": "string",
        "owner": "string",
        "private": true,
        "anonymousComments": true,
        "canRead": [
          "string"
        ],
        "canWrite": [
          "string"
        ],
        "comments": [
          "string"
        ],
        "deleted": false,
        "type": "Null",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {},
        "parent": "string",
        "children": [
          "string"
        ],
        "ancestors": [
          "string"
        ],
        "transform": [
          0
        ]
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
    "baseProperties": {},
    "globalMeasures": {},
    "isComputedResult": false,
    "viewerLayers": [
      {}
    ],
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "streamId": "string",
      "name": "string",
      "objects": [
        {
          "_id": "string",
          "owner": "string",
          "private": true,
          "anonymousComments": true,
          "canRead": [
            "string"
          ],
          "canWrite": [
            "string"
          ],
          "comments": [
            "string"
          ],
          "deleted": false,
          "type": "Null",
          "hash": "hash",
          "geometryHash": "Type.hash",
          "applicationId": "GUID",
          "properties": {},
          "parent": "string",
          "children": [
            "string"
          ],
          "ancestors": [
            "string"
          ],
          "transform": [
            0
          ]
        }
      ],
      "layers": [
        {
          "name": "string",
          "guid": "string",
          "orderIndex": 0,
          "startIndex": 0,
          "objectCount": 0,
          "topology": "string",
          "properties": {
            "color": {
              "a": 1,
              "hex": "string"
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
      "baseProperties": {},
      "globalMeasures": {},
      "isComputedResult": false,
      "viewerLayers": [
        {}
      ],
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/streams/{streamId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/streams/{streamId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "string",
      "properties": {
        "color": {
          "a": 1,
          "hex": "string"
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
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [
    {}
  ],
  "parent": "string",
  "children": [
    "string"
  ],
  "ancestors": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/streams/{streamId}',
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

result = RestClient.put 'http://localhost:3000/api/v1/streams/{streamId}',
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

r = requests.put('http://localhost:3000/api/v1/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}");
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

Updates a stream.

> Body parameter

```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ],
  "layers": [
    {
      "name": "string",
      "guid": "string",
      "orderIndex": 0,
      "startIndex": 0,
      "objectCount": 0,
      "topology": "string",
      "properties": {
        "color": {
          "a": 1,
          "hex": "string"
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
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [
    {}
  ],
  "parent": "string",
  "children": [
    "string"
  ],
  "ancestors": [
    "string"
  ]
}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
body|body|[SpeckleStream](#schemaspecklestream)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/v1/streams/{streamId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/api/v1/streams/{streamId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}',
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

fetch('http://localhost:3000/api/v1/streams/{streamId}',
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

result = RestClient.delete 'http://localhost:3000/api/v1/streams/{streamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/api/v1/streams/{streamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}");
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

Deletes a specific stream.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamGetObjects

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/streams/{streamId}/objects \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/streams/{streamId}/objects HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}/objects',
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

fetch('http://localhost:3000/api/v1/streams/{streamId}/objects',
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

result = RestClient.get 'http://localhost:3000/api/v1/streams/{streamId}/objects',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/streams/{streamId}/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}/objects");
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

*StreamGetObjects*

Gets stream objects.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
query|query|string|false|Specifiy which fields to retrieve, filters, limits, etc.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseObject](#schemaresponseobject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamClone

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/streams/{streamId}/clone \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/streams/{streamId}/clone HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}/clone',
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

fetch('http://localhost:3000/api/v1/streams/{streamId}/clone',
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

result = RestClient.post 'http://localhost:3000/api/v1/streams/{streamId}/clone',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('http://localhost:3000/api/v1/streams/{streamId}/clone', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}/clone");
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

Clones a stream.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ],
  "clone": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "streamId": "string",
    "name": "string",
    "objects": [
      {
        "_id": "string",
        "owner": "string",
        "private": true,
        "anonymousComments": true,
        "canRead": [
          "string"
        ],
        "canWrite": [
          "string"
        ],
        "comments": [
          "string"
        ],
        "deleted": false,
        "type": "Null",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {},
        "parent": "string",
        "children": [
          "string"
        ],
        "ancestors": [
          "string"
        ],
        "transform": [
          0
        ]
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
    "baseProperties": {},
    "globalMeasures": {},
    "isComputedResult": false,
    "viewerLayers": [
      {}
    ],
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ]
  },
  "parent": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "streamId": "string",
    "name": "string",
    "objects": [
      {
        "_id": "string",
        "owner": "string",
        "private": true,
        "anonymousComments": true,
        "canRead": [
          "string"
        ],
        "canWrite": [
          "string"
        ],
        "comments": [
          "string"
        ],
        "deleted": false,
        "type": "Null",
        "hash": "hash",
        "geometryHash": "Type.hash",
        "applicationId": "GUID",
        "properties": {},
        "parent": "string",
        "children": [
          "string"
        ],
        "ancestors": [
          "string"
        ],
        "transform": [
          0
        ]
      }
    ],
    "layers": [
      {
        "name": "string",
        "guid": "string",
        "orderIndex": 0,
        "startIndex": 0,
        "objectCount": 0,
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
    "baseProperties": {},
    "globalMeasures": {},
    "isComputedResult": false,
    "viewerLayers": [
      {}
    ],
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ]
  }
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStreamClone](#schemaresponsestreamclone)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## StreamDiff

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId}',
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

fetch('http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/streams/{streamId}/diff/{otherStreamId}");
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

`GET /streams/{streamId}/diff/{otherStreamId}`

*StreamDiff*

Diffs two streams (objects and layers).

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
streamId|path|string|true|No description
otherStreamId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ],
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
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
        "topology": "string",
        "properties": {
          "color": {
            "a": 1,
            "hex": "string"
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
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStreamDiff](#schemaresponsestreamdiff)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

# Objects

Create, get and update objects.

## ObjectCreate

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/objects \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/objects HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '[
  {}
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/objects',
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

result = RestClient.post 'http://localhost:3000/api/v1/objects',
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

r = requests.post('http://localhost:3000/api/v1/objects', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects");
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

Create one or more objects

> Body parameter

```json
[
  {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  }
]
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
body|body|array[SpeckleObject]|false|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseObject](#schemaresponseobject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectUpdate

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/objects/{objectId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/objects/{objectId} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects/{objectId}',
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
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [
    "string"
  ],
  "canWrite": [
    "string"
  ],
  "comments": [
    "string"
  ],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [
    "string"
  ],
  "ancestors": [
    "string"
  ],
  "transform": [
    0
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/objects/{objectId}',
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

result = RestClient.put 'http://localhost:3000/api/v1/objects/{objectId}',
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

r = requests.put('http://localhost:3000/api/v1/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects/{objectId}");
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

Update a object

> Body parameter

```json
{}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description
body|body|[SpeckleObject](#schemaspeckleobject)|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseObject](#schemaresponseobject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectGet

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/api/v1/objects/{objectId} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/api/v1/objects/{objectId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects/{objectId}',
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

fetch('http://localhost:3000/api/v1/objects/{objectId}',
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

result = RestClient.get 'http://localhost:3000/api/v1/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/api/v1/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects/{objectId}");
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

Get a object

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseObject](#schemaresponseobject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectDelete

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/api/v1/objects/{objectId} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/api/v1/objects/{objectId} HTTP/1.1
Host: localhost:3000

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects/{objectId}',
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

fetch('http://localhost:3000/api/v1/objects/{objectId}',
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

result = RestClient.delete 'http://localhost:3000/api/v1/objects/{objectId}',
  params: {
  }, headers: headers

p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/api/v1/objects/{objectId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects/{objectId}");
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

Deletes an object

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectUpdateProperties

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/api/v1/objects/{objectId}/properties \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/api/v1/objects/{objectId}/properties HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects/{objectId}/properties',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/objects/{objectId}/properties',
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

result = RestClient.put 'http://localhost:3000/api/v1/objects/{objectId}/properties',
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

r = requests.put('http://localhost:3000/api/v1/objects/{objectId}/properties', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects/{objectId}/properties");
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

`PUT /objects/{objectId}/properties`

*ObjectUpdateProperties*

Does a merge update of the object's properties.

> Body parameter

```json
{}
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
objectId|path|string|true|No description
body|body|object|true|An object that holds the keys you want to modify or add.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>

## ObjectGetBulk

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/api/v1/objects/getbulk \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/api/v1/objects/getbulk HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://localhost:3000/api/v1/objects/getbulk',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '[
  "string"
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('http://localhost:3000/api/v1/objects/getbulk',
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

result = RestClient.post 'http://localhost:3000/api/v1/objects/getbulk',
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

r = requests.post('http://localhost:3000/api/v1/objects/getbulk', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://localhost:3000/api/v1/objects/getbulk");
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

`POST /objects/getbulk`

*ObjectGetBulk*

Gets a load of objects

> Body parameter

```json
[
  "string"
]
```
### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
query|query|string|false|Specifiy which fields to retrieve, filters, limits, etc. For example, `?fields=type,properties,hash&type=Circle`
body|body|array[string]|true|An object that holds the keys you want to modify or add.


> Example responses

```json
{
  "success": true,
  "message": "string",
  "resource": {
    "_id": "string",
    "owner": "string",
    "private": true,
    "anonymousComments": true,
    "canRead": [
      "string"
    ],
    "canWrite": [
      "string"
    ],
    "comments": [
      "string"
    ],
    "deleted": false,
    "type": "Null",
    "hash": "hash",
    "geometryHash": "Type.hash",
    "applicationId": "GUID",
    "properties": {},
    "parent": "string",
    "children": [
      "string"
    ],
    "ancestors": [
      "string"
    ],
    "transform": [
      0
    ]
  },
  "resources": [
    {
      "_id": "string",
      "owner": "string",
      "private": true,
      "anonymousComments": true,
      "canRead": [
        "string"
      ],
      "canWrite": [
        "string"
      ],
      "comments": [
        "string"
      ],
      "deleted": false,
      "type": "Null",
      "hash": "hash",
      "geometryHash": "Type.hash",
      "applicationId": "GUID",
      "properties": {},
      "parent": "string",
      "children": [
        "string"
      ],
      "ancestors": [
        "string"
      ],
      "transform": [
        0
      ]
    }
  ]
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [
    {}
  ]
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseObject](#schemaresponseobject)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKey
</aside>



