---
layout: page
title: Company - REST API Documentation
---

<ol itemprop="breadcrumb">
<li><a href="/">Support</a></li>
<li><a href="/developers">Developers</a></li>
<li><a href="/developers/api">API</a></li>
<li><a href="/developers/api/company">Company Methods</a></li>
</ol>

# Companies - API Methods

This end point returns the company information for the currently user
#TODO Some pre content for this section

### Single Company
<pre>
    <code class="endpoint">GET https://dev.akkroo.com/api/company</code>
</pre>

<pre>
    <code class="payload">GET /api/company HTTP/1.1
Authorization: Bearer <span class="highlight">&lt;client credentials&gt;</span>
Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
</code>
</pre>


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
	"id": returned company id,
	"themeDefault":"returned theme default",
	"themeAvailable":"returned available themes",
	"lastModified":"Fri, 17 May 2013 16:17:37 +0100",
	"name":"returned company name",
	"appPasscode":"returned app pass code",
	"companyCSS":"returned company css",
	"urlHash":"returned url hash",
	"username":"returned username",
	"accountExpires":null
}</code></pre>

The API returned the company details for the currently authorised credentials

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