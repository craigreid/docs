---
layout: page
title: REST API Documentation
---

### Authentication

The API endpoints require an access token in the Authorization header of every
request.  This token is obtained with a 'client credentials' grant
[http://tools.ietf.org/html/rfc6749#section-4.4](http://tools.ietf.org/html/rfc6749#section-4.4).
This is a simple process - we will provide you with credentials to use, then you
perform a POST to the auth endpoint which will return the access token on
success.

<pre>
    <code class="endpoint">POST https://dev.akkroo.com/api/auth</code>
</pre>

<pre>
    <code class="payload">POST /api/auth HTTP/1.1
Authorization: Basic <span class="highlight">&lt;client credentials&gt;</span>
Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json

{
    "grant_type": "client_credentials",
    "username":   <span class="highlight">&lt;username&gt;"</span>,
    "scope":      "PublicAPI"
}</code>
</pre>

Here a JSON formatted body was POSTed to the endpoint with the client
credentials.

### Response

<pre><code>HTTP/1.1 200 OK
Vary: Accept-Encoding,Authorization,If-Modified-Since,If-Unmodified-Since
Server: Apache/2.2.24 (Unix)
X-UA-Compatible: IE=Edge,chrome=1
X-Server-Code: zv2CwrpNJYGANlX
Connection: Keep-Alive
Content-Type: application/vnd.akkroo-v1.1+json
Date: Wed, 15 May 2013 09:18:19 GMT
Transfer-Encoding: Identity
Keep-Alive: timeout=5, max=100
Cache-Control: no-cache, max-age=2592000
Expires: Fri, 14 Jun 2013 09:18:19 GMT

{
    "access_token": "NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA",
    "expires_in":   "1209600",
    "token_type":   "bearer",
    "scope":        "PublicAPI"
}</code></pre>

The server returned an access token which can be used to perform further API requests.