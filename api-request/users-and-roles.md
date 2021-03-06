---
description: Users and roles management API
---

# Users & Roles

{% api-method method="get" host="https://st-server.jvm" path="/api/roles" %}
{% api-method-summary %}
Get Roles
{% endapi-method-summary %}

{% api-method-description %}
Get all data roles
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Accept" type="string" required=false %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer \_\_Your\_API\_Token\_\_
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="JSON" %}
```javascript
{
    "status" : true,
    "message" : "Berhasil tampil",
    "data" : [
        {
            "id" : _ID_,
            "name" : _NAME_,
            "guard_name" : _GUARD_,
            "create_at" : _CREATE_,
            "update_at" : _UPDATE_
        }
    ]
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://st-server.jvm" path="/api/role" %}
{% api-method-summary %}
Add Role
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer \_\_Your\_API\_Token\_\_
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=false %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Unique
{% endapi-method-parameter %}

{% api-method-parameter name="permission" type="array" required=true %}
you can add like this permission\[\] or the data array block
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Success add new role
{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="JSON" %}
```javascript
{
    "status" : true,
    "message" : "Berhasil tambah role",
    "data" : null
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://st-server.jvm" path="/api/profile/add" %}
{% api-method-summary %}
Add profile
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://st-server.jvm" path="/api/register" %}
{% api-method-summary %}
Add User
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer \_\_Your\_API\_Token\_\_
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=false %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Username, white space will be replace to underscore \_
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email, unique
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password for your account
{% endapi-method-parameter %}

{% api-method-parameter name="confirm-password" type="string" required=true %}
Equals to password
{% endapi-method-parameter %}

{% api-method-parameter name="roles" type="array" required=true %}
roles\[\] - Add roles to user
{% endapi-method-parameter %}

{% api-method-parameter name="contact\_id" type="integer" required=true %}
Contact id, get from contacts list
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Success response
{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="JSON" %}
```javascript
{
    "status": true,
    "message": "Berhasil tampil",
    "data": {
        "name": "cemol",
        "email": "cemol@cemol.sapa",
        "password": "__PASSWORD__",
        "confirm-password": "__PASSWORD__",
        "roles": [
            "1", "admin"
        ],
        "contact_id": "3"
    }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

