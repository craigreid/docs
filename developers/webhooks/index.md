---
layout: page
title: Webhooks – Akkroo
---

<ol itemprop="breadcrumb">
<li><a href="/">Support</a></li>
<li><a href="/developers">Developers</a></li>
<li><a href="/developers/webhooks">Webhooks</a></li>
</ol>

# Webhooks

## Understanding & Using Webhooks

Webhooks are a way to tell Akkroo to call a script on your own web server when a
particular event takes place.

An example of how this might be useful is as follows,

- **Event:** new person registers at an event via Akkroo
- **Action:** Akkroo sends a message to your website asking for it to create a user account for the new person


#### Other uses could include:

- Updating a live statistics display in your office Sending a SMS message
- Printing a conference label or badge


Each of these tasks would require additional coding on your part, but Webhooks
provide a great and simple way to start extending Akkroo today.


## Libraries

<table>
    <thead>
        <tr>
            <th scope="col">Language</th>
            <th scope="col" class="width-25">Documentation</th>
            <th scope="col" class="width-25">Download</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>PHP</strong></td>
            <td><a href="https://github.com/Akkroo/APIClient">View Documentation</a></td>
            <td class="width-25"><a href="https://github.com/Akkroo/APIClient/archive/master.zip">Download Latest (ZIP)</a></td>
        </tr>
    </tbody>
</table>

We currently only provide a PHP library, however the principles are the same
across all languages, and if you are interested in working up a version in your
own language, we are keen to share any contributions you'd be willing to make public.
