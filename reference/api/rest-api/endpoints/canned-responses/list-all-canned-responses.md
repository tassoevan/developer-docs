# List All Canned Responses

<figure><img src="../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a list of all [canned responses](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses) in the workspace. It is helpful for [omnichannel managers](https://docs.rocket.chat/use-rocket.chat/omnichannel/managers) to get all canned responses in the workspace, including private and departmental canned responses. It supports the [#pagination](../../#pagination "mention") parameters.

{% hint style="info" %}
It requires the `view-canned-responses` and `view-all-canned-responses` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>



## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/canned-responses' \
--header 'x-auth-token: Ja29cTtF-wkmq32z2zmy8defFiezECIBCBysrknSoYf' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```javascript
{
    "cannedResponses": [
        {
            "_id": "646c747ca8c3a3ba32d0e2e8",
            "shortcut": "Denied",
            "text": "This is an example",
            "scope": "global",
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T08:08:28.241Z",
            "_updatedAt": "2023-05-23T08:08:28.241Z"
        },
        {
            "_id": "646c6ed9a8c3a3ba32d0e2db",
            "shortcut": "my-new-canned",
            "text": "This is an example",
            "scope": "global",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T07:44:25.912Z",
            "_updatedAt": "2023-05-23T07:44:25.912Z"
        },
        {
            "_id": "646c7350a8c3a3ba32d0e2e0",
            "shortcut": "my-new-canned-",
            "text": "This is an example",
            "scope": "hi",
            "tags": [
                "failed",
                "card"
            ],
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-23T08:03:28.148Z",
            "_updatedAt": "2023-05-23T08:03:28.148Z"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-canned-responses` and `view-all-canned-responses` permission.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
