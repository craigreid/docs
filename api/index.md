---
layout: page
title: REST API Documentation
---


# REST API Documentation

The Akkroo API is currently under development and currently access is granted on
a case-by-case basis, however we are actively working towards a public release.

In the meanwhile, you may be able to implement based on our
[Webhook feature](/docs/webhooks) which is already available, or you can request
access by sending an e-mail to [support@akkroo.com](mailto:support@akkroo.com).


### Authentication

The API endpoints require an access token in the Authorization header of every
request.  This token is obtained with a 'client credentials' grant
[http://tools.ietf.org/html/rfc6749#section-4.4](http://tools.ietf.org/html/rfc6749#section-4.4).
This is a simple process - we will provide you with credentials to use, then you
perform a POST to the auth endpoint which will return the access token on
success.


    POST https://dev.akkroo.com/api/auth


    POST /api/auth HTTP/1.1
    Authorization: Basic <client credentials>
    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json

    {
        "grant_type": "client_credentials",
        "username":   "<username>",
        "scope":      "PublicAPI"
    }

Here a JSON formatted body was POSTed to `/api/auth` with the client
credentials. The server returned an access token which can be used to perform
further API requests.

### Response

    HTTP/1.1 200 OK
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
    }





### API endpoints

Now we have an access token we can GET a list of events:

    GET /api/events HTTP/1.1
    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json
    Authorization: Bearer NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA


    HTTP/1.1 200 OK
    Last-Modified: Tue, 19 Mar 2013 11:44:57 +0000
    Keep-Alive: timeout=5, max=100
    Content-Type: application/vnd.akkroo-v1.1+json
    Server: Apache/2.2.24 (Unix)
    X-Server-Code: zv2CwrpNJYGANlX
    Expires: Wed, 15 May 2013 10:47:16 +0100
    Transfer-Encoding: Identity
    Cache-Control: max-age=30, must-revalidate, private
    Date: Wed, 15 May 2013 09:46:46 GMT
    Connection: Keep-Alive
    X-UA-Compatible: IE=Edge,chrome=1
    Vary: Authorization,Accept-Encoding,If-Modified-Since,If-Unmodified-Since
    Content-Range: resources 0-10/10

    [
        {
            "id":   118,
            "name": "Event name",
            "type": 3,
            "date": "2012-10-01",
            "lastModified": "Thu, 14 Mar 2013 15:56:01 +0000",
            "questions": [
                {
                    "type": "text",
                    "id":"textfield",
                    "required":true,
                    "label":"Enter three letters then three numbers",
                    "initialVal":"ABC123",
                    "pattern":"[a-zA-Z]{3}[0-9]{3}",
                    "minLength":3,
                    "maxLength":7,
                    "placeholder":"Enter text",
                    "multiline":false,
                    "autoCapitalize":"off",
                    "autoCorrect":"off"
                },
                {
                    "type":"email",
                    "id":"email",
                    "required":true,
                    "initialVal":"dss@zdsd.com",
                    "label":"Email address",
                    "placeholder":"email",
                    "successMessage":"well done",
                    "warningMessage":"Please enter a personal email address"
                },
                {
                    "type":"date",
                    "id":"date",
                    "required":true,
                    "initialVal":"1992-01-01",
                    "label":"please enter a date",
                    "dateType":"date",
                    "minVal":"1920-01-01",
                    "maxVal":"2011-12-31"
                },
                {
                    "type":"select",
                    "id":"select",
                    "required":true,
                    "label":"Please select 3",
                    "options":
                    [
                        "One",
                        {
                            "value":"2",
                            "label":"Two",
                            "initialVal":true
                        },
                        {
                            "label":"Three",
                            "initialVal":true
                        },
                        {
                            "label":"Option Group",
                            "options":
                            [
                                {
                                    "value":"4",
                                    "label":"Four",
                                    "initialVal":true
                                },
                                "five"
                            ]
                        }
                    ],
                    "multiSelect":"true",
                    "minLength":2,
                    "maxLength":4
                },
                {
                    "type":"checkbox",
                    "id":"emailMe",
                    "initialVal":true,
                    "label":"Tick to send email"
                },
                {
                    "type":"checkboxGroup",
                    "id":"checkboxGroup",
                    "label":"please check 3",
                    "checkboxes":
                    [
                        {
                            "id":"one",
                            "label":"Number one",
                            "initialVal":true
                        },
                        {
                            "id":"two",
                            "label":"Number two"
                        },
                        {
                            "id":"three",
                            "label":"Number three",
                            "initialVal":true
                        },
                        {
                            "id":"four",
                            "label":"Number four"
                        },
                        {
                            "id":"five",
                            "label":"Number five"
                        }
                    ],
                    "minLength":2,
                    "maxLength":4
                },
                {
                    "type":"radio",
                    "id":"radio",
                    "required":true,
                    "initialVal":"one",
                    "label":"Please select one",
                    "radioButtons":
                    [
                        {
                            "id":"one",
                            "label":"number one"
                        },
                        {
                            "id":"two",
                            "label":"number two"
                        },
                        {
                            "id":"three",
                            "label":"number three"
                        }
                    ]
                },
                {
                    "type":"label",
                    "id":"label",
                    "label":"Test label"
                },
                {
                    "type":"number",
                    "id":"number",
                    "required":true,
                    "label":"Please enter a number \u003E1000 \u003C10000",
                    "initialVal":5000,
                    "minVal":1000,
                    "maxVal":10000,
                    "step":1
                },
                {
                    "type":"range",
                    "id":"range",
                    "required":true,
                    "label":"Please enter a number",
                    "initialVal":5,
                    "minVal":0,
                    "maxVal":10,
                    "step":1
                },
                {
                    "type":"tel",
                    "id":"telephone",
                    "required":true,
                    "label":"Telephone number",
                    "initialVal":"07932343123"
                },
                {
                    "type":"url",
                    "id":"url",
                    "required":true,
                    "label":"URL Required",
                    "initialVal":"http:\/\/sdsfd.com"
                },
                {
                    "type":"text",
                    "id":"fullName",
                    "required":true,
                    "initialVal":"joe bloggs",
                    "label":"enter your name",
                    "minLength":5,
                    "maxLength":15
                },
                {
                    "type":"twitter",
                    "id":"twitter",
                    "initialVal":"nrbrook",
                    "required":true,
                    "label":"Twitter username"
                }
            ]
        }
    ]

A GET request was performed on the `/api/events` endpoint, which fetches all the
events in the system.  An array of event objects is returned. Shown here is just
the first event. I've removed some of the attributes from the response that
aren't really appropriate for you. I suppose the only important ones for you
really are `name` and `id`. The `questions` array forms the majority of the
response, defining the questions that are asked in the App.

Once you have all the events, you can GET the registrations for a specific event
by specifying the event ID in the url:

    GET /api/events/118/registrations HTTP/1.1
    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json
    Authorization: Bearer NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA


    HTTP/1.1 200 OK
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
    ]

A GET request was performed on the registrations endpoint which returned an
array of all the registrations.  The important attribute here is "values" which
contains the responses to the questions asked in the App.  The keys of the
object are the field IDs.  The value is an object containing a `value`
attribute, which is the value for the field.  Some values may be an array, if
they are from a set of checkboxes for example, see the `select` value.

The registrations collection endpoint can also accept a POST containing data
with the same JSON format:

    POST /api/events/118/registrations HTTP/1.1
    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json
    Authorization: Bearer NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA

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
        "timeArrived": 1361546439237,
        "isCheckIn": false
    }


    HTTP/1.1 201 Created
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
    }


There are also error responses which I have not documented here, but hopefully
this will give you an idea of how you can integrate with the API. If you have
any questions on this let me know.
