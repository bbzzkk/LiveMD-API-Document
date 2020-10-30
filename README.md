---
description: 'Assignee: 정소영'
---

# Document \(문서관리\)

{% api-method method="post" host="https://livemd.com" path="/api/v1/documents/:uid" %}
{% api-method-summary %}
Create User Documents
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create new documents with specific user.  
You have to check authorization of creating documents from team server.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uid" type="string" required=false %}
id of user who creates new documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="docId" type="string" required=true %}
documents id which is made by client automatically.
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
    result: true,
    status: 200,
    data: {
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{
    "status": "404",
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents/:uid" %}
{% api-method-summary %}
Get All User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get all documents of specific user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uid" type="string" required=true %}
id of user who created documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="sort" type="string" required=false %}
value can be..  
ex: id, created\_at, DESC
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" required=false %}
page size
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="number" required=false %}
a number of pages
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
    data: [
    {
        id: "id",
        uid: "uid",
        docid: "docid",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        },
        id: "id2",
        uid: "uid2",
        docid: "docid2",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        }]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "404",
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents/:docid" %}
{% api-method-summary %}
Get One of User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get one of specific user documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific document
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
        id: "id",
        tid: "uid",
        docid: "docid",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "404",
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://livemd.com" path="/api/v1/documents/:docid" %}
{% api-method-summary %}
Update Title of User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to update title of user documents.  
You have to check authorization of updating title from team server.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="title" type="string" required=true %}
title to be updated
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "404",
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://livemd.com" path="/api/v1/documents/:docid" %}
{% api-method-summary %}
Delete User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to delete user documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "404",
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://livemd.com" path="/api/v1/documents/:tid" %}
{% api-method-summary %}
Create Team Documents
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create new documents with specific team.  
You have to check authorization of creating documents from team server.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="tid" type="string" required=false %}
id of team who creates new documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    result: true,
    status: 200,
    data: {
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    
    "status": "404"
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents/:tid" %}
{% api-method-summary %}
Get All Team Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get all documents of specific user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="tid" type="string" required=true %}
id of team who created documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
    data: [
    {
        id: "id",
        tid: "tid",
        docid: "docid",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        },
        id: "id2",
        tid: "tid2",
        docid: "docid2",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        }]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{    
    "status": "404"
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://livemd.com/api" path="/v1/documents/:docid" %}
{% api-method-summary %}
Get One of Team Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get one of specific team documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific document
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
        id: "id",
        tid: "tid",
        docid: "docid",
        title: "title,
        content: "content",
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{    
    "status": "404"
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://livemd.com" path="/api/v1/documents/:docid" %}
{% api-method-summary %}
Update Title of Team Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to update title of user documents.  
You have to check authorization of updating title from team server.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{    
    "status": "404"
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://livemd.com" path="/api/v1/documents/:docid" %}
{% api-method-summary %}
Delete Team Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to delete team documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docid" type="string" required=true %}
id of specific documents
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
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
        "docid" : "id"}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{    
    "status": "404"
    "result": "false"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



