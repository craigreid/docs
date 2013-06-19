---
layout: page
title: REST API Events Documentation
---

# Events


## List Events

Returns a list of events in the Akkroo system for the current user.

    GET https://dev.akkroo.com/api/events

Headers required for api endpoint

    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json
    Authorization: Bearer <Authorisation Token>

### Response

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

### Single Event

Returns the event details for the individual event id thats passed to it

    GET https://dev.akkroo.com/api/events/:event_id

Headers required for api endpoint

    Accept: application/vnd.akkroo-v1.1+json
    Content-Type: application/vnd.akkroo-v1.1+json
    Authorization: Bearer <Authorisation Token>

###Response


	{
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
	}
