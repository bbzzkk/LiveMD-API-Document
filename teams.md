---
description: 'assignee: 이연주'
---

# Teams \(팀관리\)

{% api-method method="post" host="https://api.livemd.com" path="/api/v1/teams" %}
{% api-method-summary %}
Post Team by user id
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="actions" type="string" required=true %}
create
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="thumbnail" type="string" required=false %}
This field means thumbnail of team.
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
This field means name of team.
{% endapi-method-parameter %}

{% api-method-parameter name="userId" type="string" required=true %}
This field means owner of team. He will be added to team member.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
This field means description of team.
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
    result: true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.livemd.com" path="/api/v1/teams" %}
{% api-method-summary %}
Get All Teams by user id
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="userId" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    result: true,
    status: 200,
    data: [{
        name: "bbzzkk",
        thumbnail-small: "http://~~~"
    },
    {
        name: "happyBirthday",
        thumbnail-small: "http://~~~"
    },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.livemd.com" path="/api/v1/teams/:teamId" %}
{% api-method-summary %}
Get One Team by team name 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="teamId" type="string" required=true %}
This field means team id which have already been registered
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    result: true,
    status: 200,
    data: {
        name: "bbzzkk",
        description: "LiveMD markdown editior service",
        thumbnail-small: "http://~~~",
        thumbnail-big: "http://~~",
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://api.livemd.com" path="/api/v1/teams/:teamId" %}
{% api-method-summary %}
Update Team information
{% endapi-method-summary %}

{% api-method-description %}
Type of Team information  
- thumbnail  
- description 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="teamId" type="string" required=true %}
This field means team id which have already been registered.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="thumbnail" type="string" required=false %}
This field means thumbnail of team. We must be check whether this request is for updating thumbnail because of S3 costs. 
{% endapi-method-parameter %}

{% api-method-parameter name="userId" type="string" required=true %}
This field means user id whose request to update. This must be check authorization of this team.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
This field means description of team.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.livemd.com" path="/api/v1/teams/:teamId" %}
{% api-method-summary %}
Delete Team
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="teamId" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="userId" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

