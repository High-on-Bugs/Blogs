---
title: "REST and REST API - Part 3"
datePublished: Mon Mar 06 2023 08:54:25 GMT+0000 (Coordinated Universal Time)
cuid: clewl5xws000k09mpha7v2uch
slug: rest-part-3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678044005456/4c51084a-2cc5-4fd5-a327-a4693c8a2003.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678092855461/e53a38e8-8470-4237-8d62-c3f1c5bd1028.png
tags: rest, apis, restful, rest-api, postmanapi

---

You will need to go through the [1st](https://highonbugs.sbk2k1.me/rest-part-1) and [2nd](https://highonbugs.sbk2k1.me/rest-part-2) blogs to get what's happening here.

Endpoint: [https://hob-api.vercel.app/](https://hob-api.vercel.app/)

GitHub repository: [https://github.com/sbk2k1/API-Blog](https://github.com/sbk2k1/API-Blog)

---

## /get Routes

GET HTTP requests are used to retrieve or fetch data from a server. This is typically used when a user requests to view a webpage or retrieve specific data from a server. Constraints include limited data storage capacity in the URL, which can impact the size of data that can be sent in a GET request, and the fact that GET requests are typically visible in browser histories and can be cached, which can impact security. Additionally, GET requests are not suitable for sending sensitive information, such as passwords or other authentication credentials, in the URL. A GET request implemented using REST does not have a request body.

Create a new request in Postman or your browser as shown below:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678028074617/72f97f79-a25b-465a-b590-36ec181976b6.png align="center")

Fire it off!

If you get a Status 200 OK response, you'll probably get a response body like this:

```json
{
    "error": false,
    "message": "Get Request Received Successfully",
    "query_parameters": {},
    "bearer_token": "Bearer Token is absent",
    "headers": {
        "host": "hob-api.vercel.app",
        "x-real-ip": "xx.xxx.xxx.xxx",
        "x-vercel-proxy-signature-ts": "xxxxxxxxx8",
        "x-vercel-deployment-url": "hob-o362hip79-sbk2k1.vercel.app",
        "x-vercel-ip-latitude": "xx.xxx",
        "x-vercel-forwarded-for": "xx.xxx.xxx.xxx",
        "x-vercel-id": "bom1::xv4kk-1678028068902-ec68b76f258e",
        "forwarded": "for=xx.2xx.xx5.xxx;host=hob-api.vercel.app;proto=https;sig=0QmVhcmVyIDVhMDRiOGY1MmNkNjE0YTE4Zjc4Yjc3Y2Q1YWU5NmYzYWQ0MzVjMWNXXXXXXXXXXXXXjc0MTcwOGU=;exp=1678028368",
        "postman-token": "xxxfxxxx-5e47-xxxa-a51a-xxxxxx43a60e",
        "x-vercel-ip-longitude": "x8.xxx2",
        "accept": "*/*",
        "x-forwarded-for": "xx.xxx.xxx.xxx",
        "x-forwarded-host": "hob-api.vercel.app",
        "x-vercel-ip-country": "IN",
        "x-forwarded-proto": "https",
        "x-vercel-proxy-signature": "Bearer 5a04b8f52xxxxxxxxxxxxxxxxxxxx6f3ad435cxxxxxxxxxdbecd0d01eaff741708e",
        "accept-encoding": "gzip, deflate, br",
        "user-agent": "PostmanRuntime/x.xx.4",
        "x-vercel-ip-country-region": "WB",
        "x-vercel-ip-city": "Kolkata",
        "x-vercel-ip-timezone": "Asia/Kolkata",
        "x-vercel-proxied-for": "xx.xxx.xxx.1x4",
        "connection": "close"
    }
}
```

Here's a breakdown of each part of the response:

* `"error": false`: This indicates that there was no error in processing the request.
    
* `"message": "Get Request Received Successfully"`: This is a custom message returned by the server to indicate that the GET request was received successfully.
    
* `"query_parameters": {}`: This is an empty object indicating that there were no query parameters included in the GET request.
    
* `"bearer_token": "Bearer Token is absent"`: This indicates that no bearer token was included in the request.
    
* `"headers": { ... }`: This is an object containing information about the headers included in the GET request. Each key-value pair in this object represents a single header and its value.
    

Some of the headers included in this response include:

* `"host": "`[`hob-api.vercel.app`](http://hob-api.vercel.app)`"`: This is the hostname of the server that received the request.
    
* `"x-real-ip": "xx.xxx.xxx.xxx"`: This is the IP address of the client that made the request.
    
* `"x-vercel-deployment-url": "`[`hob-o362hip79-sbk2k1.vercel.app`](http://hob-o362hip79-sbk2k1.vercel.app)`"`: This is the URL of the Vercel deployment that is handling the request.
    
* `"x-forwarded-proto": "https"`: This indicates that the request was made over HTTPS.
    
* `"user-agent": "PostmanRuntime/7.28.4"`: This is the user agent string of the client that made the request.
    
* `"connection": "close"`: This indicates that the connection will be closed after the response is sent.
    

### Setting path and query parameters and bearer token

1. Let us configure the URL as such: (You can also add query params from the params tab)
    

```bash
https://hob-api.vercel.app/get/2?id=2&isDarkMode=true
```

1. Go to the "Headers" tab below the URL and set a new field called `Authorization` and set any value to it. I'm setting "This is my Authorization Token"
    

This is what the request looks like:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678028471343/cbfb6613-6c30-46d6-9b5e-6c26a27dd1ba.png align="center")

On firing it, this is what it looks like,

```json
{
    "error": false,
    "message": "Get Request Received Successfully",
    "path_parameter": "2 is the path parameter",
    "query_parameters": {
        "id": "2",
        "isDarkMode": "true"
    },
    "bearer_token": "This is my Authorization Token",
    "headers": {
        "host": "hob-api.vercel.app",
        "authorization": "This is my Authorization Token",
        "x-real-ip": "45.250.245.184",
        "x-vercel-proxy-signature-ts": "1678028816",
        "x-vercel-deployment-url": "hob-o362hip79-sbk2k1.vercel.app",
        "x-vercel-ip-latitude": "22.518",
        "x-vercel-forwarded-for": "45.250.245.184",
        "x-vercel-id": "bom1::xq858-1678028516261-e4cf9d6423ef",
        "forwarded": "for=45.250.245.184;host=hob-api.vercel.app;proto=https;sig=0QmVhcmVyIDdmN2Y1MmI3NGNhMDRjNDUxYmQ1MDA5YzljOWNiNWMwMDIzMjJiZmZlYjc0MDZkMGE2MThiYjNkYmViNzQyY2M=;exp=1678028816",
        "postman-token": "2c80ebc4-74cd-44c3-af96-72f27b0c67c5",
        "x-vercel-ip-longitude": "88.3832",
        "accept": "*/*",
        "x-forwarded-for": "45.250.245.184",
        "x-forwarded-host": "hob-api.vercel.app",
        "x-vercel-ip-country": "IN",
        "x-vercel-ip-country-region": "WB",
        "x-vercel-proxy-signature": "Bearer 7f7f52b74ca04c451bd5009c9c9cb5c002322bffeb7406d0a618bb3dbeb742cc",
        "accept-encoding": "gzip, deflate, br",
        "user-agent": "PostmanRuntime/7.28.4",
        "x-forwarded-proto": "https",
        "x-vercel-ip-city": "Kolkata",
        "x-vercel-ip-timezone": "Asia/Kolkata",
        "x-vercel-proxied-for": "45.250.245.184",
        "connection": "close"
    }
}
```

Describing the fields and what they are used for:

* **Query parameters**: These are extra data passed in the URL of an HTTP request to filter or modify the response. They are commonly used to paginate, sort, or filter data, and are often visible in the URL bar of the browser. They are passed through the endpoint using "?" followed by parameters separated by a "&".
    
* **Path parameters**: These are parts of the URL that represent a dynamic value. They are often used to identify a specific resource and can be used to make more meaningful and memorable URLs. These parameters are set using any value after the endpoint route using a "/".
    
* **Authentication header**: This is a request header that contains an authentication token or credentials to prove the identity of the requester. It is commonly used to secure APIs and web applications and ensures that only authorized users have access to protected resources. They may contain encrypted data to check if the routes are accessible by a certain type of client entity.
    

**NOTE: We will not be explaining path and query parameters or the authentication header/other headers anymore moving forward.**

---

## /post Routes

HTTP POST is a request method that is used to submit an entity to the specified resource, often causing a change in state or side effects on the server. The main purpose of the HTTP POST method is to create a new resource or to update an existing resource on the server.

The constraints for HTTP POST requests are:

* The request payload must contain the entity that will be created or updated on the server.
    
* The POST method may cause side effects, such as the creation of a new resource or the modification of an existing one.
    
* Unlike GET requests, POST requests are not cacheable.
    
* POST requests are typically used for creating, updating, or deleting resources on the server, so they require proper authentication and authorization.
    

Create a new request in Postman or your browser as shown below:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678087885468/d4d1d221-18ce-471c-af84-ba33146ff55d.png align="center")

Go to the Body tab, select "raw" and then "JSON" from the drop-down. Enter any random data or paste the following body

```json
{
"field_1": 1,
"name": "sbk2k1",
"github": "github.com/sbk2k1"
}
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678089879423/9417f18c-79d5-459b-8b2f-34c3252359a0.png align="center")

Fire it off! The response looks like this if everything was 200 OK.

```json
{
    "error": false,
    "message": "Post Request Received Successfully",
    "body": {
        "field_1": 1,
        "name": "sbk2k1",
        "github": "github.com/sbk2k1"
    },
    "query_parameters": {},
    "bearer_token": "Bearer Token is absent",
    "headers": {
        ...
    }
}
```

In a POST request, the body of the request contains the data that is being sent to the server. This data can be in various formats such as JSON, XML, or plain text. The purpose of the body is to provide additional information to the server beyond the URL and headers, which are used to route the request and provide metadata about the request, respectively. The body is particularly useful for sending data to the server for processing, such as creating or updating a resource, submitting a form, or uploading a file. You can see the body you sent through the request. In an actual working backend, the body can be saved to an external database.

---

## /put Routes

A PUT request is an HTTP method that is used to update an existing resource on the server. It is similar to the POST request, but it is used to modify an existing resource rather than create a new one.

The constraints of a PUT request are similar to that of a POST request. It requires that the client has the proper authorization to modify the resource, and it is idempotent, meaning that making multiple identical requests will have the same effect as a single request.

The body of a PUT request typically contains the updated representation of the resource being modified. This means that the client must send the entire representation of the resource, including any fields that have not changed.

One of the primary constraints of a PUT request is that it replaces the entire resource at the given URL. If the client only wants to update a specific field or subset of fields, a PATCH request should be used instead. Additionally, if the client is unsure if the resource already exists on the server, a POST request should be used instead of a PUT request.

**NOTE: The PATCH method is not inherently dangerous, but it can be risky if not used carefully. The main reason is that PATCH requests are designed to make partial updates to an existing resource, rather than replacing it entirely. If the PATCH request is not crafted correctly, it could potentially overwrite important data, leading to unintended consequences or security vulnerabilities. Additionally, since PATCH is a less commonly used HTTP method, some systems may not support it or may handle it differently, which could lead to compatibility issues. This blog does not include PATCH functionality.**

Change the request in Postman to a **/put** route and fire it off. It should look like this. We are using the same data as the post request.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678090631989/285c458f-dfa9-4257-bb00-b916e3d5ca0a.png align="center")

The 200 OK response should look something like this.

```json
{
    "error": false,
    "message": "Put Request Received Successfully",
    "body": {
        "field_1": 1,
        "name": "sbk2k1",
        "github": "github.com/sbk2k1"
    },
    "query_parameters": {},
    "bearer_token": "Bearer Token is absent",
    "headers": {
        ...
    }
}
```

---

## /delete Routes

The DELETE HTTP method is used to delete a resource identified by a URI (Uniform Resource Identifier). It is used to remove a resource from the server. The DELETE method is idempotent, which means that making the same request multiple times will produce the same result as making the request only once.

In RESTful API design, the DELETE method typically does not have a body because the resource to be deleted is identified by the URI. The server deletes the resource identified by the URI, and the response status code indicates the success or failure of the operation.

To specify the resource to be deleted, the client includes the resource's identifier in the URI. For example, a DELETE request to [`https://example.com/api/users/123`](https://example.com/api/users/123) would delete the user with the ID of 123. If the resource to be deleted cannot be found, the server returns a 404 Not Found status code. (Status code refresher [here](https://highonbugs.sbk2k1.me/rest-part-1))

Load up the request as shown below.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678092386726/ac89195f-02ea-4d84-afe9-4b0d4af94ee1.png align="center")

The 200 OK response is as follows.

```json
{
    "error": false,
    "message": "Delete Request Received Successfully",
    "query_parameters": {},
    "bearer_token": "Bearer Token is absent",
    "headers": {
        ...
    }
}
```

**NOTE: You can add a bearer token, query, or path parameters to any of the requests. I've simply skipped these for the brevity of this blog.**

In conclusion, the four HTTP methods, GET, POST, PUT, and DELETE, serve different purposes in REST API design. GET is used to retrieve resources, POST to create new resources, PUT to update or replace existing resources, and DELETE to remove resources. Each method has its constraints and use cases that are important to consider when designing a RESTful API. Understanding the differences between these methods is crucial for creating effective and efficient APIs.

---

You may have understood the different technicalities, but this blog still does not highlight how these APIs are used in an actual application. Stay tuned for another series in which we will go through building an entire app and will show all implementations, code structure, and security/authentication measures commonly used. This should have provided you with a clear view of what REST APIs and REST are. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!