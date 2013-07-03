---
layout: page
title: REST API Events Documentation
---

# Events

## Create Event


## List All Events

Returns a list of events in the Akkroo system for the current user.

<pre><code class="endpoint">GET https://dev.akkroo.com/api/events</code></pre>

Headers required for api endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span>
</code></pre>

<h3>Response</h3>

<pre><code>HTTP/1.1 200 OK
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
]</code></pre>

A GET request was performed on the `/api/events` endpoint, which fetches all the
events in the system.  An array of event objects is returned. Shown here is just
the first event. I've removed some of the attributes from the response that
aren't really appropriate for you. I suppose the only important ones for you
really are `name` and `id`. The `questions` array forms the majority of the
response, defining the questions that are asked in the App.

### Fields
<table class="endpoint-field-parameters">
    <tr>
        <td class="field-id">access_token</td><td class='field-value'>
            <div class="code-example">"access_token": "NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">expires_in</td><td class='field-value'>
            <div class="code-example">"expires_in": "123123"</div>
            <div class="code-description">time field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">token_type</td><td class='field-value'>
            <div class="code-example">"token_type": "bearer"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">scope</td><td class='field-value'>
            <div class="code-example">"scope": "PublicAPI"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
</table>

### List Single Event

Returns the event details for the individual event id thats passed to it

<pre>
    <code class="endpoint">GET https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span></code>
</pre>

Headers required for api endpoint

<pre>
<code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span>
</code>
</pre>

###Response

<pre>
    <code>{
"id":118,
"name":"name",
"type":1,
"date":"2013-06-19",
"eventCSS":null,
"styleJSON":"{\n    \u0022id\u0022: \u0022name91\u0022\n}",
"resourceName":"51ae1a9a9cf1751ae1a9a9f62d",
"pureMessageName":null,
"pureListName":null,
"pureFieldRemap":"",
"brandingImageResourceName":"testlogo.png",
"checkinCancelButton":"Not Me...",
"checkinConfirmButton":"Yes, that\u0027s me!",
"checkinToolbarTitle":"Check in",
"combinedLandingNo":"No",
"combinedLandingQuestion":"Did you register before the event?",
"combinedLandingYes":"Yes",
"doneButton":"Done",
"doneMessage":"We\u0027ve saved your details and sent you an email with more info.",
"doneToolbarTitle":"Thanks!",
"lastModified":"Thu, 14 Mar 2013 15:56:01 +0000",
"questions":[
	{
		"type":"text",
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
		"options":[
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
			"options":[
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
		"checkboxes":[
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
		"radioButtons":[
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
],
"registerButton":"Register",
"registerToolbarTitle":"Register",
"selectOneButton":"Checkin"
}</code></pre>

### Fields
<table class="endpoint-field-parameters">
    <tr>
        <td class="field-id">access_token</td><td class='field-value'>
            <div class="code-example">"access_token": "NmZhOTQwODU0ZDUxMzBjYzBjNDIwYzk4ZTQwN2NkOGEwZWM3OTZiNjk4YTc3YjY5NTY4YzQ1YWYzOTcxMGM2NA"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">expires_in</td><td class='field-value'>
            <div class="code-example">"expires_in": "123123"</div>
            <div class="code-description">time field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">token_type</td><td class='field-value'>
            <div class="code-example">"token_type": "bearer"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">scope</td><td class='field-value'>
            <div class="code-example">"scope": "PublicAPI"</div>
            <div class="code-description">String field</div>
        </td>
    </tr>
</table>

## List Registrations

Returns a list of events in the Akkroo system for the current user.

<pre><code class="endpoint">GET https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers required for api endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span></code></pre>

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

## List Checkins

Returns a list of events checkins for a event

<pre><code class="endpoint">GET https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers required for api endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span></code></pre>

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

### Create Registration

Creates a new registration item in the akkroo system

<pre><code class="endpoint">POST https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers Required for this endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span></code></pre>

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

### Fields
<table class="endpoint-field-parameters">
    <tr><td class="field-id">textfield</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">email</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">date</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">select</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">emailMe</td><td class='field-value'>something here</td></tr>
    <tr>
        <td class="field-id">checkboxGroup</td>
        <td class='field-value'>

        </td>
    </tr>
    <tr>
        <td class="field-id">isCheckIn</td><td class='field-value'> 
            <div class="code-example">"isCheckIn": false</div>
            <div class="code-description">Boolean field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">timeArrived</td><td class='field-value'>
            <div class="code-example"> "timeArrived": 1361546439237</div>
            <div class="code-description">This should be a timestamp field</div>
        </td>
    </tr>
</table>

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

### Create Checkin

Creates a new checkin item in the akkroo system

<pre><code class="endpoint">POST https://dev.akkroo.com/api/events/<span class="highlight">:event_id</span>/registrations</code></pre>

Headers Required for this endpoint

<pre><code>Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
Authorization: Bearer <span class="highlight">&lt;Authorisation Token&gt;</span></code></pre>

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
        "isCheckIn": true
    }</code></pre>

### Fields
<table class="endpoint-field-parameters">
    <tr><td class="field-id">textfield</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">email</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">date</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">select</td><td class='field-value'>something here</td></tr>
    <tr><td class="field-id">emailMe</td><td class='field-value'>something here</td></tr>
    <tr>
        <td class="field-id">checkboxGroup</td>
        <td class='field-value'>

        </td>
    </tr>
    <tr>
        <td class="field-id">isCheckIn</td><td class='field-value'> 
            <div class="code-example">"isCheckIn": false</div>
            <div class="code-description">Boolean field</div>
        </td>
    </tr>
    <tr>
        <td class="field-id">timeArrived</td><td class='field-value'>
            <div class="code-example"> "timeArrived": 1361546439237</div>
            <div class="code-description">This should be a timestamp field</div>
        </td>
    </tr>
</table>

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

### Bulk Checkins

## TODO not sure if this is in the API or not

### Bulk Registrations

## TODO not sure if this is in the api or not 