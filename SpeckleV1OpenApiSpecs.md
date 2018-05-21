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
headingLevel: 2


---


<h1 id="Speckle-OpenApi-Specs">Speckle OpenApi Specs v1.0.0-beta</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


Documentation & specifications for the Speckle Server & Speckle Objects.


Base URLs:


* <a href="http://localhost:3000/api/v1">http://localhost:3000/api/v1</a>


* <a href="https://localhost:3000/api/v1">https://localhost:3000/api/v1</a>


Email: <a href="mailto:hello@speckle.works">SpeckleWorks</a> Web: <a href="https://speckle.works">SpeckleWorks</a> 


# Authentication


* API Key (JWT_Token_Auth)
    - Parameter Name: **Authorization**, in: header. 


<h1 id="Speckle-OpenApi-Specs-Accounts">Accounts</h1>


Register, Login and more.


## UserRegister


<a id="opIdUserRegister"></a>


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
  "logins": []
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
  "logins": []
}
```


<h3 id="UserRegister-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserRegister-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed to register a new user.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## UserLogin


<a id="opIdUserLogin"></a>


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
  "logins": []
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
  "logins": []
}
```


<h3 id="UserLogin-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|The only required elements are email and password.|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserLogin-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|You've logged in.|[ResponseUser](#schemaresponseuser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## UserSearch


<a id="opIdUserSearch"></a>


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
  "logins": []
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
  "logins": []
}
```


<h3 id="UserSearch-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserSearch-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## UserGet


<a id="opIdUserGet"></a>


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
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## UserUpdateProfile


<a id="opIdUserUpdateProfile"></a>


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
  "logins": []
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
  "logins": []
}
```


<h3 id="UserUpdateProfile-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserUpdateProfile-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Things are looking good yo.|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## UserGetProfileById


<a id="opIdUserGetProfileById"></a>


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


<h3 id="UserGetProfileById-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="UserGetProfileById-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|New user successfully registered.|[ResponseUser](#schemaresponseuser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


<h1 id="Speckle-OpenApi-Specs-Clients">Clients</h1>


Create, get and update application clients.


## ClientGetAll


<a id="opIdClientGetAll"></a>


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
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ClientGetAll-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ClientCreate


<a id="opIdClientCreate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
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


<h3 id="ClientCreate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AppClient](#schemaappclient)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ClientCreate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ClientUpdate


<a id="opIdClientUpdate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
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


<h3 id="ClientUpdate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|clientId|path|string|true|No description|
|body|body|[AppClient](#schemaappclient)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ClientUpdate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseClient](#schemaresponseclient)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ClientGet


<a id="opIdClientGet"></a>


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


<h3 id="ClientGet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|clientId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ClientGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseClient](#schemaresponseclient)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ClientDelete


<a id="opIdClientDelete"></a>


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


<h3 id="ClientDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|clientId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ClientDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


<h1 id="Speckle-OpenApi-Specs-Projects">Projects</h1>


Create, get and update projects.


## ProjectGetAll


<a id="opIdProjectGetAll"></a>


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
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ProjectGetAll-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseProject](#schemaresponseproject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ProjectCreate


<a id="opIdProjectCreate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "name": "string",
  "number": "string",
  "users": [],
  "streams": [],
  "subProjects": []
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


*Create*


Create a project


> Body parameter


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "name": "string",
  "number": "string",
  "users": [],
  "streams": [],
  "subProjects": []
}
```


<h3 id="ProjectCreate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Project](#schemaproject)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ProjectCreate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's clients.|[ResponseProject](#schemaresponseproject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ProjectUpdate


<a id="opIdProjectUpdate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "name": "string",
  "number": "string",
  "users": [],
  "streams": [],
  "subProjects": []
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "name": "string",
  "number": "string",
  "users": [],
  "streams": [],
  "subProjects": []
}
```


<h3 id="ProjectUpdate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|projectId|path|string|true|No description|
|body|body|[Project](#schemaproject)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ProjectUpdate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseProject](#schemaresponseproject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ProjectGet


<a id="opIdProjectGet"></a>


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


<h3 id="ProjectGet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|projectId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ProjectGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseProject](#schemaresponseproject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ProjectDelete


<a id="opIdProjectDelete"></a>


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


<h3 id="ProjectDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|projectId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ProjectDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


<h1 id="Speckle-OpenApi-Specs-Comments">Comments</h1>


Create, get and update comments.


## CommentCreate


<a id="opIdCommentCreate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "resource": {},
  "text": "string",
  "assignedTo": [],
  "closed": true,
  "labels": [],
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "resource": {},
  "text": "string",
  "assignedTo": [],
  "closed": true,
  "labels": [],
  "view": {},
  "screenshot": "string"
}
```


<h3 id="CommentCreate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|resourceType|path|string|true|The resource type you want to comment on.|
|resourceId|path|string|true|The resource id you want to comment on. In the case of streams, it must be a streamId.|
|body|body|[Comment](#schemacomment)|true|No description|


#### Enumerated Values


|Parameter|Value|
|---|---|
|resourceType|stream|
|resourceType|object|
|resourceType|project|
|resourceType|comment|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="CommentCreate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## CommentGetFromResource


<a id="opIdCommentGetFromResource"></a>


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


<h3 id="CommentGetFromResource-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|resourceType|path|string|true|The resource type you want to comment on.|
|resourceId|path|string|true|The resource id you want to comment on. In the case of streams, it must be a streamId.|


#### Enumerated Values


|Parameter|Value|
|---|---|
|resourceType|stream|
|resourceType|object|
|resourceType|project|
|resourceType|comment|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="CommentGetFromResource-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## CommentGet


<a id="opIdCommentGet"></a>


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


<h3 id="CommentGet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|commentId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="CommentGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseComment](#schemaresponsecomment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## CommentUpdate


<a id="opIdCommentUpdate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "resource": {},
  "text": "string",
  "assignedTo": [],
  "closed": true,
  "labels": [],
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "resource": {},
  "text": "string",
  "assignedTo": [],
  "closed": true,
  "labels": [],
  "view": {},
  "screenshot": "string"
}
```


<h3 id="CommentUpdate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|commentId|path|string|true|No description|
|body|body|[Comment](#schemacomment)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="CommentUpdate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## CommentDelete


<a id="opIdCommentDelete"></a>


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


<h3 id="CommentDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|commentId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="CommentDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


<h1 id="Speckle-OpenApi-Specs-Streams">Streams</h1>


Create, get and update streams.


## StreamsGetAll


<a id="opIdStreamsGetAll"></a>


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
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamsGetAll-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamCreate


<a id="opIdStreamCreate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [],
  "layers": [],
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [],
  "parent": "string",
  "children": [],
  "ancestors": []
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [],
  "layers": [],
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [],
  "parent": "string",
  "children": [],
  "ancestors": []
}
```


<h3 id="StreamCreate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SpeckleStream](#schemaspecklestream)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamCreate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamGet


<a id="opIdStreamGet"></a>


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


<h3 id="StreamGet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|
|query|query|string|false|Specifiy which fields to retrieve, ie `?fields=layers,baseProperties`.|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStream](#schemaresponsestream)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamUpdate


<a id="opIdStreamUpdate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [],
  "layers": [],
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [],
  "parent": "string",
  "children": [],
  "ancestors": []
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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [],
  "layers": [],
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [],
  "parent": "string",
  "children": [],
  "ancestors": []
}
```


<h3 id="StreamUpdate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|
|body|body|[SpeckleStream](#schemaspecklestream)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamUpdate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamDelete


<a id="opIdStreamDelete"></a>


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


<h3 id="StreamDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamGetObjects


<a id="opIdStreamGetObjects"></a>


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


<h3 id="StreamGetObjects-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|
|query|query|string|false|Specifiy which fields to retrieve, filters, limits, etc.|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamGetObjects-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseObject](#schemaresponseobject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamClone


<a id="opIdStreamClone"></a>


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


<h3 id="StreamClone-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [],
  "clone": {},
  "parent": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamClone-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStreamClone](#schemaresponsestreamclone)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## StreamDiff


<a id="opIdStreamDiff"></a>


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


<h3 id="StreamDiff-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|streamId|path|string|true|No description|
|otherStreamId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [],
  "objects": {},
  "layers": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="StreamDiff-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseStreamDiff](#schemaresponsestreamdiff)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


<h1 id="Speckle-OpenApi-Specs-Objects">Objects</h1>


Create, get and update objects.


## ObjectCreate


<a id="opIdObjectCreate"></a>


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
  {}
]
```


<h3 id="ObjectCreate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|false|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectCreate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseObject](#schemaresponseobject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ObjectUpdate


<a id="opIdObjectUpdate"></a>


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
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": []
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
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": []
}
```


<h3 id="ObjectUpdate-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|objectId|path|string|true|No description|
|body|body|[SpeckleObject](#schemaspeckleobject)|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectUpdate-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All the users's projects.|[ResponseObject](#schemaresponseobject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ObjectGet


<a id="opIdObjectGet"></a>


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


<h3 id="ObjectGet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|objectId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectGet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The client.|[ResponseObject](#schemaresponseobject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ObjectDelete


<a id="opIdObjectDelete"></a>


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


<h3 id="ObjectDelete-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|objectId|path|string|true|No description|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectDelete-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ObjectUpdateProperties


<a id="opIdObjectUpdateProperties"></a>


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


<h3 id="ObjectUpdateProperties-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|objectId|path|string|true|No description|
|body|body|object|true|An object that holds the keys you want to modify or add.|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectUpdateProperties-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


## ObjectGetBulk


<a id="opIdObjectGetBulk"></a>


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


<h3 id="ObjectGetBulk-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Specifiy which fields to retrieve, filters, limits, etc. For example, `?fields=type,properties,hash&type=Circle`|
|body|body|array[string]|true|An object that holds the keys you want to modify or add.|


> Example responses


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```
```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


<h3 id="ObjectGetBulk-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All good!|[ResponseObject](#schemaresponseobject)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Fail whale.|[ResponseBase](#schemaresponsebase)|


<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
JWT_Token_Auth
</aside>


# Schemas


<h2 id="tocSresourcebase">ResourceBase</h2>


<a id="schemaresourcebase"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|_id|string|false|No description|
|owner|string|false|No description|
|private|boolean|false|No description|
|anonymousComments|boolean|false|No description|
|canRead|[string]|false|No description|
|canWrite|[string]|false|No description|
|comments|[string]|false|An array of comment ids.|
|deleted|boolean|false|Controls archival status - does not actually delete anything|


<h2 id="tocSuser">User</h2>


<a id="schemauser"></a>


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
  "logins": []
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|_id|string|false|Database uuid.|
|role|string|false|User's role. Defaults to "user".|
|avatar|string|false|We will need profile pics at one point.|
|apitoken|string|false|a signed jwt token that expires in 1 year.|
|token|string|false|a signed jwt token that expires in 1 day.|
|email|string|false|user's email|
|name|string|false|User's given name|
|surname|string|false|User's family name|
|company|string|false|Users's company|
|logins|[object]|false|an array storing each time the user logged in.|
|» date|string|false|No description|


<h2 id="tocSappclient">AppClient</h2>


<a id="schemaappclient"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
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


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResourceBase](#schemaresourcebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» _id|string|false|Database uuid.|
|» role|string|false|Either Sender, Receiver or anything else you can think of.|
|» documentGuid|string|false|No description|
|» documentName|string|false|No description|
|» documentType|string|false|No description|
|» documentLocation|string|false|No description|
|» streamId|string|false|The streamId that this client is attached to.|
|» online|boolean|false|Is it accessible from the server or not?|


<h2 id="tocSproject">Project</h2>


<a id="schemaproject"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "name": "string",
  "number": "string",
  "users": [],
  "streams": [],
  "subProjects": []
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResourceBase](#schemaresourcebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» _id|string|false|No description|
|» name|string|false|No description|
|» number|string|false|No description|
|» users|[string]|false|No description|
|» streams|[string]|false|No description|
|» subProjects|[string]|false|No description|


<h2 id="tocScomment">Comment</h2>


<a id="schemacomment"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "resource": {},
  "text": "string",
  "assignedTo": [],
  "closed": true,
  "labels": [],
  "view": {},
  "screenshot": "string"
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResourceBase](#schemaresourcebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|object|false|No description|
|»» resourceType|string|false|No description|
|»» resourceId|string|false|No description|
|» text|string|false|No description|
|» assignedTo|[string]|false|No description|
|» closed|boolean|false|No description|
|» labels|[string]|false|No description|
|» view|object|false|No description|
|» screenshot|string|false|No description|


<h2 id="tocSspecklestream">SpeckleStream</h2>


<a id="schemaspecklestream"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "streamId": "string",
  "name": "string",
  "objects": [],
  "layers": [],
  "baseProperties": {},
  "globalMeasures": {},
  "isComputedResult": false,
  "viewerLayers": [],
  "parent": "string",
  "children": [],
  "ancestors": []
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResourceBase](#schemaresourcebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» streamId|string|false|The stream's short id.|
|» name|string|false|The data stream's name|
|» objects|[[SpeckleObject](#schemaspeckleobject)]|false|An array of SpeckleObject ids.|
|» layers|[[Layer](#schemalayer)]|false|An array of speckle layers.|
|» baseProperties|object|false|Units, tolerances, etc.|
|» globalMeasures|object|false|Any performance measures can go in here.|
|» isComputedResult|boolean|false|No description|
|» viewerLayers|[object]|false|No description|
|» parent|string|false|If this stream is a child, the parent's streamId.|
|» children|[string]|false|An array of the streamId of any children of this stream.|
|» ancestors|[string]|false|If resulting from a merge, the streams that this one was born out of.|


<h2 id="tocSlayer">Layer</h2>


<a id="schemalayer"></a>


```json
{
  "name": "string",
  "guid": "string",
  "orderIndex": 0,
  "startIndex": 0,
  "objectCount": 0,
  "topology": "string",
  "properties": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|Layer's name|
|guid|string|false|Layer's guid (must be unique)|
|orderIndex|integer|false|Describes this layer's position in the list of layers.|
|startIndex|number|false|The index of the first object relative to the stream's objects array|
|objectCount|number|false|How many objects does this layer have.|
|topology|string|false|String describing the nested tree structure (GH centric).|
|properties|[LayerProperties](#schemalayerproperties)|false|No description|


<h2 id="tocSlayerproperties">LayerProperties</h2>


<a id="schemalayerproperties"></a>


```json
{
  "color": {},
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


|Name|Type|Required|Description|
|---|---|---|---|
|color|object|false|No description|
|» a|number|false|alpha value|
|» hex|string|false|hex color value|
|visible|boolean|false|toggles layer visibility.|
|pointsize|number|false|defines point size in threejs|
|linewidth|number|false|defines line thickness in threejs|
|shininess|number|false|says it all. speckle is superficial.|
|smooth|boolean|false|smooth shading toggle|
|showEdges|boolean|false|display edges or not yo.|
|wireframe|boolean|false|i'm bored.|


<h2 id="tocSresponsebase">ResponseBase</h2>


<a id="schemaresponsebase"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": []
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|success|boolean|false|Besides the http status code, this tells you whether the call succeeded or not.|
|message|string|false|Either an error or a confirmation.|
|resource|object|false|Returned resource (if querying by id)|
|resources|[object]|false|Returned resources array (if it's a bulk query)|


<h2 id="tocSresponseuser">ResponseUser</h2>


<a id="schemaresponseuser"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[User](#schemauser)|false|No description|
|» resources|[[User](#schemauser)]|false|No description|


<h2 id="tocSresponseclient">ResponseClient</h2>


<a id="schemaresponseclient"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[AppClient](#schemaappclient)|false|No description|
|» resources|[[AppClient](#schemaappclient)]|false|No description|


<h2 id="tocSresponseproject">ResponseProject</h2>


<a id="schemaresponseproject"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[Project](#schemaproject)|false|No description|
|» resources|[[Project](#schemaproject)]|false|No description|


<h2 id="tocSresponsecomment">ResponseComment</h2>


<a id="schemaresponsecomment"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[Comment](#schemacomment)|false|No description|
|» resources|[[Comment](#schemacomment)]|false|No description|


<h2 id="tocSresponsestream">ResponseStream</h2>


<a id="schemaresponsestream"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[SpeckleStream](#schemaspecklestream)|false|No description|
|» resources|[[SpeckleStream](#schemaspecklestream)]|false|No description|


<h2 id="tocSresponseobject">ResponseObject</h2>


<a id="schemaresponseobject"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» resource|[SpeckleObject](#schemaspeckleobject)|false|No description|
|» resources|[[SpeckleObject](#schemaspeckleobject)]|false|No description|


<h2 id="tocSresponsestreamclone">ResponseStreamClone</h2>


<a id="schemaresponsestreamclone"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [],
  "clone": {},
  "parent": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» clone|[SpeckleStream](#schemaspecklestream)|false|No description|
|» parent|[SpeckleStream](#schemaspecklestream)|false|No description|


<h2 id="tocSresponsestreamdiff">ResponseStreamDiff</h2>


<a id="schemaresponsestreamdiff"></a>


```json
{
  "success": true,
  "message": "string",
  "resource": {},
  "resources": [],
  "objects": {},
  "layers": {}
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResponseBase](#schemaresponsebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» objects|object|false|No description|
|»» common|[string]|false|No description|
|»» inA|[string]|false|No description|
|»» inB|[string]|false|No description|
|» layers|object|false|No description|
|»» common|[[Layer](#schemalayer)]|false|No description|
|»» inA|[[Layer](#schemalayer)]|false|No description|
|»» inB|[[Layer](#schemalayer)]|false|No description|


<h2 id="tocSspeckleobject">SpeckleObject</h2>


<a id="schemaspeckleobject"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": []
}
```


### Properties


*allOf*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[ResourceBase](#schemaresourcebase)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|string|false|Object's subtype|
|» hash|string|false|Object's unique hash.|
|» geometryHash|string|false|Object's geometry hash|
|» applicationId|string|false|The id/guid that the origin application identifies this object by.|
|» properties|object|false|The extra properties field of a speckle object.|
|» parent|string|false|If this object is a child, the parent's objectid.|
|» children|[string]|false|An array of the ids of any children of this object.|
|» ancestors|[string]|false|If resulting from a merge, the objects that this one was born out of.|
|» transform|[number]|false|No description|


#### Enumerated Values


|Property|Value|
|---|---|
|type|Null|
|type|Abstract|
|type|Placeholder|
|type|Boolean|
|type|Number|
|type|String|
|type|Interval|
|type|Interval2d|
|type|Point|
|type|Vector|
|type|Plane|
|type|Line|
|type|Rectangle|
|type|Circle|
|type|Arc|
|type|Ellipse|
|type|Polycurve|
|type|Box|
|type|Polyline|
|type|Curve|
|type|Mesh|
|type|Brep|
|type|Annotation|
|type|Extrusion|


<h2 id="tocSspeckleabstract">SpeckleAbstract</h2>


<a id="schemaspeckleabstract"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Abstract",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "_type": "string",
  "assembly": "string"
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» _type|string|false|the original type of the object|
|» assembly|string|false|the original assembly of this object|


<h2 id="tocSspeckleplaceholder">SpecklePlaceholder</h2>


<a id="schemaspeckleplaceholder"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Abstract",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": []
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|


<h2 id="tocSspeckleboolean">SpeckleBoolean</h2>


<a id="schemaspeckleboolean"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Boolean",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": true
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|boolean|false|No description|


<h2 id="tocSspecklenumber">SpeckleNumber</h2>


<a id="schemaspecklenumber"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Number",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": 0
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|number|false|A number. Can be float, double, etc.|


<h2 id="tocSspecklestring">SpeckleString</h2>


<a id="schemaspecklestring"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "String",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": "string"
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|string|false|A string.|


<h2 id="tocSspeckleinterval">SpeckleInterval</h2>


<a id="schemaspeckleinterval"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Interval",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "start": 0,
  "end": 0
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» start|number|false|No description|
|» end|number|false|No description|


<h2 id="tocSspeckleinterval2d">SpeckleInterval2d</h2>


<a id="schemaspeckleinterval2d"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "U": {},
  "V": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» U|[SpeckleInterval](#schemaspeckleinterval)|false|No description|
|» V|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklepoint">SpecklePoint</h2>


<a id="schemaspecklepoint"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Point",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": []
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|[number]|false|An array containing the X, Y and Z coords of the point.|


<h2 id="tocSspecklevector">SpeckleVector</h2>


<a id="schemaspecklevector"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Vector",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": []
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|[number]|false|An array containing the X, Y and Z coords of the vector.|


<h2 id="tocSspeckleplane">SpecklePlane</h2>


<a id="schemaspeckleplane"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Plane",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "origin": {},
  "normal": {},
  "xdir": {},
  "ydir": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» origin|[SpecklePoint](#schemaspecklepoint)|false|No description|
|» normal|[SpeckleVector](#schemaspecklevector)|false|No description|
|» xdir|[SpeckleVector](#schemaspecklevector)|false|No description|
|» ydir|[SpeckleVector](#schemaspecklevector)|false|No description|


<h2 id="tocSspecklecircle">SpeckleCircle</h2>


<a id="schemaspecklecircle"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Circle",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "radius": 0,
  "center": {},
  "normal": {},
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» radius|number|false|No description|
|» center|[SpecklePoint](#schemaspecklepoint)|false|No description|
|» normal|[SpeckleVector](#schemaspecklevector)|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklearc">SpeckleArc</h2>


<a id="schemaspecklearc"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Arc",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "radius": 0,
  "startAngle": 0,
  "endAngle": 0,
  "angleRadians": 0,
  "plane": {},
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» radius|number|false|No description|
|» startAngle|number|false|No description|
|» endAngle|number|false|No description|
|» angleRadians|number|false|No description|
|» plane|[SpecklePlane](#schemaspeckleplane)|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspeckleellipse">SpeckleEllipse</h2>


<a id="schemaspeckleellipse"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Ellipse",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "firstRadius": 0,
  "secondRadius": 0,
  "plane": {},
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» firstRadius|number|false|No description|
|» secondRadius|number|false|No description|
|» plane|[SpecklePlane](#schemaspeckleplane)|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklepolycurve">SpecklePolycurve</h2>


<a id="schemaspecklepolycurve"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Polycurve",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "segments": [],
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» segments|[[SpeckleObject](#schemaspeckleobject)]|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklebox">SpeckleBox</h2>


<a id="schemaspecklebox"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Box",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "basePlane": {},
  "xSize": {},
  "ySize": {},
  "zSize": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» basePlane|[SpecklePlane](#schemaspeckleplane)|false|No description|
|» xSize|[SpeckleInterval](#schemaspeckleinterval)|false|No description|
|» ySize|[SpeckleInterval](#schemaspeckleinterval)|false|No description|
|» zSize|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspeckleline">SpeckleLine</h2>


<a id="schemaspeckleline"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Line",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "value": [],
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» value|[number]|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklepolyline">SpecklePolyline</h2>


<a id="schemaspecklepolyline"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Polyline",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "closed": true,
  "value": [],
  "domain": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» closed|boolean|false|No description|
|» value|[number]|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|


<h2 id="tocSspecklecurve">SpeckleCurve</h2>


<a id="schemaspecklecurve"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Curve",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "degree": 0,
  "periodic": true,
  "rational": true,
  "points": [],
  "weights": [],
  "knots": [],
  "domain": {},
  "displayValue": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» degree|number|false|No description|
|» periodic|boolean|false|No description|
|» rational|boolean|false|No description|
|» points|[number]|false|No description|
|» weights|[number]|false|No description|
|» knots|[number]|false|No description|
|» domain|[SpeckleInterval](#schemaspeckleinterval)|false|No description|
|» displayValue|[SpecklePolyline](#schemaspecklepolyline)|false|No description|


<h2 id="tocSspecklemesh">SpeckleMesh</h2>


<a id="schemaspecklemesh"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Mesh",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "vertices": [],
  "faces": [],
  "colors": [],
  "textureCoordinates": []
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» vertices|[number]|false|The mesh's vertices array, in a flat array (ie, `x1, y1, z1, x2, y2, ...`)|
|» faces|[number]|false|The faces array.|
|» colors|[number]|false|If any, the colours per vertex.|
|» textureCoordinates|[number]|false|The faces array.|


<h2 id="tocSspecklebrep">SpeckleBrep</h2>


<a id="schemaspecklebrep"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Brep",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "rawData": {},
  "provenance": "string",
  "displayValue": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» type|any|false|No description|
|» rawData|object|false|The brep's raw (serialisation) data.|
|» provenance|string|false|A short prefix of where the base64 comes from.|
|» displayValue|[SpeckleMesh](#schemaspecklemesh)|false|No description|


<h2 id="tocSspeckleextrusion">SpeckleExtrusion</h2>


<a id="schemaspeckleextrusion"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "capped": true,
  "profile": {},
  "pathStart": {},
  "pathEnd": {},
  "pathCurve": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» capped|boolean|false|No description|
|» profile|[SpeckleObject](#schemaspeckleobject)|false|No description|
|» pathStart|[SpecklePoint](#schemaspecklepoint)|false|No description|
|» pathEnd|[SpecklePoint](#schemaspecklepoint)|false|No description|
|» pathCurve|[SpeckleObject](#schemaspeckleobject)|false|No description|


<h2 id="tocSspeckleannotation">SpeckleAnnotation</h2>


<a id="schemaspeckleannotation"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "text": "string",
  "textHeight": 0,
  "fontName": "string",
  "bold": true,
  "italic": true,
  "location": {},
  "plane": {}
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» text|string|false|No description|
|» textHeight|number|false|No description|
|» fontName|string|false|No description|
|» bold|boolean|false|No description|
|» italic|boolean|false|No description|
|» location|[SpecklePoint](#schemaspecklepoint)|false|No description|
|» plane|[SpecklePlane](#schemaspeckleplane)|false|No description|


<h2 id="tocSspeckleblock">SpeckleBlock</h2>


<a id="schemaspeckleblock"></a>


```json
{
  "_id": "string",
  "owner": "string",
  "private": true,
  "anonymousComments": true,
  "canRead": [],
  "canWrite": [],
  "comments": [],
  "deleted": false,
  "type": "Null",
  "hash": "hash",
  "geometryHash": "Type.hash",
  "applicationId": "GUID",
  "properties": {},
  "parent": "string",
  "children": [],
  "ancestors": [],
  "transform": [],
  "name": "string",
  "description": "string",
  "objects": []
}
```


### Properties


*allOf - discriminator: SpeckleObject.type*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[SpeckleObject](#schemaspeckleobject)|false|No description|


*and*


|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» name|string|false|No description|
|» description|string|false|No description|
|» objects|[[SpeckleObject](#schemaspeckleobject)]|false|No description|


