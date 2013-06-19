---
layout: page
title: REST API Events Documentation
---

# Registrations


## List Event Registrations

Returns a list of events in the Akkroo system for the current user.

<pre><code class="endpoint">GET https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers required for api endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer &lt;Authorisation Token&gt;</code></pre>

### Response

<pre><code>HTTP/1.1 200 OK
Vary: Authorization,Accept-Encoding,If-Modified-Since,If-Unmodified-Since
Content-Type: application/vnd.akkroo-v1.1+json
Server: Apache
X-Server-Code: zv2CwrpNJYGANlX
Expires: Tue, 28 May 2013 18:05:49 +0100
Transfer-Encoding: Identity
Cache-Control: max-age=30, must-revalidate, private
Date: Tue, 28 May 2013 17:05:19 GMT
Strict-Transport-Security: max-age=31536000
Connection: close
X-UA-Compatible: IE=Edge,chrome=1
Content-Range: resources 0-3/3
Last-Modified: Wed, 27 Feb 2013 14:46:07 +0000

[
    {
        "values":
        {
            "textfield":
            {
                "value": "ABC123"
            },
            "email":
            {
                "value": "username@example.com"
            },
            "date":
            {
                "value": "1992-01-01"
            },
            "select":
            {
                "value":
                [
                    "2",
                    "Three",
                    "4"
                ]
            },
            "emailMe":
            {
                "value": true
            },
            "checkboxGroup":
            {
                "value":
                [
                    "one",
                    "three"
                ]
            },
            "radio":
            {
                "value": "one"
            },
            "number":
            {
                "value": "5000"
            },
            "range":
            {
                "value": "5"
            },
            "telephone":
            {
                "value": "07932343123"
            },
            "url":
            {
                "value": "http:\/\/example.com"
            },
            "fullName":
            {
                "value": "joe bloggs"
            },
            "twitter":
            {
                "value": "nrbrook"
            }
        },
        "deviceID": 1361546417588,
        "lastModified": "Fri, 22 Feb 2013 15:20:39 +0000",
        "timeArrived":1361546439237,
        "appUserID":1,
        "companyID":"2",
        "eventID":"118",
        "isCheckIn":false,
        "source":"API",
        "APIClient":"App",
        "id":"51278cc7fd1dc9055b000000"
    }
]</code></pre>


### Create a registration

Creates a new registration item in the akkroo system

<pre><code>POST https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers Required for this endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer &lt;Authorisation Token&gt;</code></pre>

The registrations collection endpoint can also accept a POST containing data
with the same JSON format:


<pre><code>{
        "values":
        {
            "textfield":
            {
                "value": "ABC123"
            },
            "email":
            {
                "value": "username@example.com"
            },
            "date":
            {
                "value": "1992-01-01"
            },
            "select":
            {
                "value":
                [
                    "2",
                    "Three",
                    "4"
                ]
            },
            "emailMe":
            {
                "value": true
            },
            "checkboxGroup":
            {
                "value":
                [
                    "one",
                    "three"
                ]
            },
            "radio":
            {
                "value": "one"
            },
            "number":
            {
                "value": "5000"
            },
            "range":
            {
                "value": "5"
            },
            "telephone":
            {
                "value": "07932343123"
            },
            "url":
            {
                "value": "http:\/\/example.com"
            },
            "fullName":
            {
                "value": "joe bloggs"
            },
            "twitter":
            {
                "value": "nrbrook"
            }
        },
        "timeArrived": 1361546439237,
        "isCheckIn": false
    }</code></pre>

### Response

<pre><code>201 Created

Content-Type: application/vnd.akkroo-v1.1+json
Keep-Alive: timeout=5, max=100
Pragma: no-cache
Server: Apache/2.2.24 (Unix)
X-Server-Code: zv2CwrpNJYGANlX
Expires: Tue, 28 May 2013 17:38:12 +0100
Transfer-Encoding: Identity
Cache-Control: must-revalidate, no-cache, private
Location: https://local.akkroo.com/api/events/118/registrations/51a4dd741dfe1fc413000000
Date: Tue, 28 May 2013 16:38:12 GMT
Connection: Keep-Alive
X-UA-Compatible: IE=Edge,chrome=1
Vary: Authorization,Accept-Encoding,If-Modified-Since,If-Unmodified-Since

{
    "id": "51a4de221dfe1fcc1a000005"
}</code></pre>

A successful response returns a 201 created HTTP header as well as a JSON object containing the id of the registration that has been created.