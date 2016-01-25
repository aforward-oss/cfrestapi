---
title: CrossFIT REST APIs

language_tabs:

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the CrossFit API!

We have language bindings in Shell, PHP.

## Parameters

Many API methods take optional parameters. For GET requests, any parameters not specified as a segment in the
path can be passed as an HTTP query string parameter:

```
curl -i "https://api.crossfit.com/recur/api/v1/accounts/123?filter=CF&limit=10"
```

In this example, the `'123'` value is provided for `:accountid` parameter in the path while `:limit` and `:filter` are passed in the query string.

For POST, PATCH, PUT, and DELETE requests, parameters not included in the URL should be encoded as JSON with a Content-Type of 'application/json':

curl -i -u username -d '{"scopes":["public_profile"]}' https://api.crossfit.com/authorizations

## HTTP Redirects

API uses HTTP redirection where appropriate. Clients should assume that any request may result in a redirection.
Receiving an HTTP redirection is not an error and clients should follow that redirect.
Redirect responses will have a Location header field which contains the URI of the resource
to which the client should repeat the requests.

| Status Code | Name | Description |
| --- | --- | --- |
| 301 | Permanent redirection. | The URI you used to make the request has been superseded by the one specified in the Location header field. This and all future requests to this resource should be directed to the new URI. |
| 302, 307 | Temporary redirection. | The request should be repeated verbatim to the URI specified in the Location header field but clients should continue to use the original URI for future requests. |

## HTTP Verbs

Where possible, API strives to use appropriate HTTP verbs for each action.

| Verb | Description |
| --- | --- |
| GET | Retrieve a resource.
| POST | Create a resource. |
| PUT | Edit a resource |
| DELETE | Delete a resource |

## Rate Limiting

TBD


## Authentication

TBD

## Hypermedia

Requests that return multiple items will be paginated to 30 items by default. You can specify further pages with the `?page` parameter. For some resources, you can also set a custom page size with the `?per_page` parameter.

# Available APIs

## Comments

## Invoices

## Recur

