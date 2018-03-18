---
title: URLShortener.io

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript
  - java
  - php
  - python
  - go
  - swift
  

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Use API to access URLShortener.io Features. View Javascript examples in the dark area to the right. For those who use postman here is the <a target="_blank" href="https://www.getpostman.com/collections/04c039f409c7ca89e6a3"> collection </a>.


# Authentication




# Create URL

This endpoint helps create accepts a long urls, tags/category. Along with the short url you get favicon url link, title, created date, original_url in response.

HTTP Request

`POST http://urlshortener.io/create/`

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://urlshortener.io/create/",
  "method": "POST",
  "headers": {
    "Cache-Control": "no-cache",
    "Postman-Token": "0745e03e-8562-0f90-ff22-45f9582be76f"
  },
  "data": "{
  \n   \"o_url\":\"http://google.co.in\",
  \n   \"tags\":\"search,fast\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/octet-stream");
RequestBody body = RequestBody.create(mediaType, "{
\n   \"o_url\":\"http://google.co.in\",
\n   \"tags\":\"search,fast\"\n}");
Request request = new Request.Builder()
  .url("http://urlshortener.io/create/")
  .post(body)
  .addHeader("Cache-Control", "no-cache")
  .addHeader("Postman-Token", "b956f441-bb26-83a1-9678-d51caa62cbbf")
  .build();

Response response = client.newCall(request).execute();
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://urlshortener.io/create/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Postman-Token' => '629516dd-4c5b-1830-986e-f21d45e5028c',
  'Cache-Control' => 'no-cache'
));

$request->setBody('{
   "o_url":"http://google.co.in",
   "tags":"search,fast"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```python
import requests

url = "http://urlshortener.io/create/"

payload = "{
\n   \"o_url\":\"http://google.co.in\",
\n   \"tags\":\"search,fast\"\n}"
headers = {
    'Cache-Control': "no-cache",
    'Postman-Token': "360b7b63-1cd1-b4b0-777b-3f45fc464008"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```go
package main

import (
  "fmt"
  "strings"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "http://urlshortener.io/create/"

  payload := strings.NewReader("{
  \n   \"o_url\":\"http://google.co.in\",
  \n   \"tags\":\"search,fast\"\n}")

  req, _ := http.NewRequest("POST", url, payload)

  req.Header.Add("Cache-Control", "no-cache")
  req.Header.Add("Postman-Token", "219464c3-66a2-7216-20a1-472f001792d7")

  res, _ := http.DefaultClient.Do(req)

  defer res.Body.Close()
  body, _ := ioutil.ReadAll(res.Body)

  fmt.Println(res)
  fmt.Println(string(body))

}
```

```swift
import Foundation

let headers = [
  "Cache-Control": "no-cache",
  "Postman-Token": "e8fd5912-1bd6-5f0e-4d62-5a95160bd481"
]

let postData = NSData(data: "{
   "o_url":"http://google.co.in",
   "tags":"search,fast"
}".data(using: String.Encoding.utf8)!)

let request = NSMutableURLRequest(
              url: NSURL(string: "http://urlshortener.io/create/")! as URL,
              cachePolicy: .useProtocolCachePolicy,timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, 
completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
It will json response in the below format




# Get Analytics ( by date range )

This endpoint fetches analytics data based for a given date range.

HTTP Request

`POST http://urlshortener.io/clicks/<SHORTURL>/`

URL Parameters

Parameter | Description
--------- | -----------
SHORTURL  | The shorturl to be filtered based on start and end date

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://urlshortener.io/clicks/l7k9XOYK/",
  "method": "POST",
  "headers": {
    "Cache-Control": "no-cache",
    "Postman-Token": "09aac1b5-9195-00b6-1c77-045236369a76"
  },
  "data": "{
  \n  \"short_url\":\"l7k9XOYK\",
  \n  \"start_date\":\"2018-03-04\",
  \n  \"end_date\":\"2018-03-10\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/octet-stream");
RequestBody body = RequestBody.create(mediaType, "{
\n  \"short_url\":\"l7k9XOYK\",
\n  \"start_date\":\"2018-03-04\",
\n  \"end_date\":\"2018-03-10\"\n}");
Request request = new Request.Builder()
  .url("http://urlshortener.io/clicks/l7k9XOYK/")
  .post(body)
  .addHeader("Cache-Control", "no-cache")
  .addHeader("Postman-Token","32747306-99c8-d5c5-3c69-2536da2de87d")
  .build();

Response response = client.newCall(request).execute();
```
```php
<?php

$request = new HttpRequest();
$request->setUrl('http://urlshortener.io/clicks/l7k9XOYK/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Postman-Token' => '2f1c0a91-7ded-dbf3-5dde-0fedcb662613',
  'Cache-Control' => 'no-cache'
));

$request->setBody('{
  "short_url":"l7k9XOYK",
  "start_date":"2018-03-04",
  "end_date":"2018-03-10"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```python
import requests

url = "http://urlshortener.io/clicks/l7k9XOYK/"

payload = "{
\n  \"short_url\":\"l7k9XOYK\",
\n  \"start_date\":\"2018-03-04\",
\n  \"end_date\":\"2018-03-10\"\n}"
headers = {
    'Cache-Control': "no-cache",
    'Postman-Token': "f20e670b-479c-bd4b-5d95-220c6bba2164"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```go
package main

import (
  "fmt"
  "strings"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "http://urlshortener.io/clicks/l7k9XOYK/"

  payload := strings.NewReader("{
  \n  \"short_url\":\"l7k9XOYK\",
  \n  \"start_date\":\"2018-03-04\",
  \n  \"end_date\":\"2018-03-10\"\n}")

  req, _ := http.NewRequest("POST", url, payload)

  req.Header.Add("Cache-Control", "no-cache")
  req.Header.Add("Postman-Token",
   "1ab64cd0-1c6a-3925-0d18-759308bbd5d7")

  res, _ := http.DefaultClient.Do(req)

  defer res.Body.Close()
  body, _ := ioutil.ReadAll(res.Body)

  fmt.Println(res)
  fmt.Println(string(body))

}
```

```swift
import Foundation

let headers = [
  "Cache-Control": "no-cache",
  "Postman-Token": "02b87681-c792-63f2-b5a7-99d53916ba62"
]

let postData = NSData(data: "{
  "short_url":"l7k9XOYK",
  "start_date":"2018-03-04",
  "end_date":"2018-03-10"
}".data(using: String.Encoding.utf8)!)

let request = NSMutableURLRequest(
url: NSURL(string: "http://urlshortener.io/clicks/l7k9XOYK/")! as URL,
    cachePolicy: .useProtocolCachePolicy,timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(
 with: request as URLRequest,
 completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```


# Get QR Code

This endpoint generates qrcode image for the given url.

HTTP Request

`GET http://urlshortener.io/genqr/<SHORTURL>/`

URL Parameters

Parameter | Description
--------- | -----------
SHORTURL  | The qrcode image to be generated for given shorturl

It will return qrcode image as response

<img src="/static/img/bQkzKBpB.png">

