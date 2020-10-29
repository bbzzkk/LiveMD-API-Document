---
description: 'assignee: 이연주'
---

# Members\(팀원관리\)

{% api-method method="post" host="https://api.livemd.com" path="/api/v1/teams/invite" %}
{% api-method-summary %}
invite member to team 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter type="string" name="teamid" required=true %}
Team which is requested for adding members now.
{% endapi-method-parameter %}

{% api-method-parameter name="userid" type="string" required=true %}
User who requests for adding members now. It must need to check authorization of add member.
{% endapi-method-parameter %}

{% api-method-parameter name="members" type="array" required=true %}
Members who were invited by owner or admin. It must include at least one.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    status: 200,
    result: true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{
    status: 404,
    result: false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.livemd.com" path="/api/v1/teams/auth" %}
{% api-method-summary %}
get authorization of user 
{% endapi-method-summary %}

{% api-method-description %}
We need to check authorization of users to limit to access some services.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
JWT token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="teamid" type="string" required=true %}
Team which is requested for adding members now.
{% endapi-method-parameter %}

{% api-method-parameter name="userid" type="string" required=true %}
User who requests for adding members now. It must need to check authorization of add member
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
type of data  
- owner  
- admin  
- writer  
- reader
{% endapi-method-response-example-description %}

```
{
    status: 200,
    result: true,
    data: "admin"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

