---
layout: page
title: Users - REST API Documentation – Akkroo
---

<ol itemprop="breadcrumb">
<li><a href="/">Support</a></li>
<li><a href="/developers">Developers</a></li>
<li><a href="/developers/api">API</a></li>
<li><a href="/developers/api/users">User Methods</a></li>
</ol>

# Users - API Methods

<ul>
	<li><a href="/developers/api/users#single_user">Single User</a></li>
	<li><a href="/developers/api/users#create_user">Create User</a></li>
	<li><a href="/developers/api/users#update_user">Update User</a></li>	
</ul>

#TODO Some pre content for this section

### Single User
<pre>
    <code class="endpoint">GET https://dev.akkroo.com/api/appUser/<span class="highlight">:user_id</span></code>
</pre>

<pre>
    <code class="payload">GET /api/appUser/<span class="highlight">:user_id</span> HTTP/1.1
Authorization: Bearer <span class="highlight">&lt;client credentials&gt;</span>
Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
</code>
</pre>

### Response


#TODO response needs placing here.
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
</code></pre>

The server returned a individual users data

## Create User

#TODO this needs looking at im not sure if this end point is correct and what needs to be posted to it etc, the response needs looking at as well to make sure its all ok
<pre>
    <code class="endpoint">POST https://dev.akkroo.com/api/appUser/<span class="highlight">:user_id</span></code>
</pre>

<pre>
    <code class="payload">POST /api/appUser/<span class="highlight">:user_id</span> HTTP/1.1
Authorization: Bearer <span class="highlight">&lt;client credentials&gt;</span>
Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
</code>
</pre>

### Response

#TODO response needs placing here.
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
</code></pre>

As you can see a user has now been created via this api call

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

## Update User
#TODO this needs looking at im not sure if this end point is correct and what needs to be posted to it etc, the response needs looking at as well to make sure its all ok
<pre>
    <code class="endpoint">POST https://dev.akkroo.com/api/appUser/<span class="highlight">:user_id</span></code>
</pre>

<pre>
    <code class="payload">POST /api/appUser/<span class="highlight">:user_id</span> HTTP/1.1
Authorization: Bearer <span class="highlight">&lt;client credentials&gt;</span>
Accept: application/vnd.akkroo-v1.1+json
Content-Type: application/vnd.akkroo-v1.1+json
</code>
</pre>

### Response

#TODO response needs placing here.
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
</code></pre>

As you can see the user has now been succesfully updated

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