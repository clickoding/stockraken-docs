---
description: Usage for API Users and Roles management
---

# Authentication

{% api-method method="post" host="https://st-server.jvm" path="/user/login" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="remember\_me" type="boolean" required=false %}
Remember for update expire date token
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password for you account
{% endapi-method-parameter %}

{% api-method-parameter name="login" type="string" required=true %}
Username or email for user to access the application
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="JSON" %}
```javascript
{
	"status":true,
	"message":"Berhasil Login",
	"data" : {
		"is_admin":false,
		"expired_at":"YYYY-MM-DD HH:ii:ss",
		"access_token":"__YOUR_API_KEY__"
	}
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="JSON" %}
```javascript
{
    "status" : false,
    "data" : null,
    "message" : "Username atau password salah"
}

```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://st-server.jvm" path="/api/role" %}
{% api-method-summary %}
Current user roles & permissions
{% endapi-method-summary %}

{% api-method-description %}
Get current user roles and permissions
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer \_\_YOUR\_API\_TOKEN\_\_
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Sample success get user role
{% endapi-method-response-example-description %}

```javascript
{
	"status":true,
	"message":"Berhasil ambil data",
	"data" : {
		"roles" : [],
		"permissions" : []
	}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://st-server.jvm" path="/api/user" %}
{% api-method-summary %}
Current user profile
{% endapi-method-summary %}

{% api-method-description %}
Get current user profile
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer \_\_Your\_API\_key\_\_
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=false %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}
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
	"status":true,
	"message":"Berhasil ambil data",
	"data" : {
        "id": 2,
        "name": "username",
        "email": "email@email.com",
        "email_verified_at": null,
        "created_at": "2019-07-16 06:29:55",
        "updated_at": "2019-07-24 04:00:26",
        "status": 0,
        "deleted_at": null,
        "contact_id": []
	}
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

