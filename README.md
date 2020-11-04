---
description: 'Assignee: 정소영'
---

# Document \(문서관리\)

{% api-method method="post" host="https://livemd.com" path="/api/v1/documents" %}
{% api-method-summary %}
Create User Documents
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to create new documents with specific user.  
You have to check authorization of creating documents from team server.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="oid" type="string" required=true %}
id of user or team\(owner\) who creates new documents
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

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

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents" %}
{% api-method-summary %}
Get All User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get all documents of specific user.   
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
JWT
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="oid" type="string" required=true %}
id of user or team who owns the documents
{% endapi-method-parameter %}

{% api-method-parameter name="sort" type="string" required=false %}
example  
sort=createdDate, desc  
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" required=false %}
a number of contents in one page  
default size = 20
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="number" required=false %}
 page number  
default page = 0
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
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        },
        id: "id2",
        uid: "uid2",
        docid: "docid2",
        title: "title,
        created_at: "2020-10-30 04:51:39",
        modified_at: "2020-10-31 04:51:39"
        }],
         "pageable": {
        "sort": {
            "sorted": false,
            "unsorted": true,
            "empty": true
        },
        "offset": 0,
        "pageSize": 10,
        "pageNumber": 0,
        "paged": true,
        "unpaged": false
    },
    "totalElements": 18,
    "last": false,   // 마지막 페이지 여부 
    "totalPages": 2,   // 전체 페이지 갯수 총 18건 데이터 중 10개의 요청이므로 2개 페이지 존재
    "size": 10,    // 페이지 당 출력 갯수  
    "number": 0,  
    "numberOfElements": 10,  // 요청 페이지에서 조회 된 데이터의 갯수
    "sort": {
        "sorted": false,
        "unsorted": true,
        "empty": true
    },
    "first": true,   // 첫 페이지 여부
    "empty": false
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

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents/{docId}" %}
{% api-method-summary %}
Get One of User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to get one of specific user documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docId" type="string" required=true %}
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

{% api-method method="get" host="https://livemd.com" path="/api/v1/documents/search" %}
{% api-method-summary %}
Search Documents By Title
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to search documents by title using keywords. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="keyword" type="string" required=true %}
you can find documents using title keyword
{% endapi-method-parameter %}

{% api-method-parameter name="oid" type="string" required=true %}
id of user or team who owns the documents
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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

{% api-method method="put" host="https://livemd.com" path="/api/v1/documents/{docId}" %}
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
{% api-method-parameter name="docId" type="string" required=true %}
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

{% api-method method="delete" host="https://livemd.com" path="/api/v1/documents/{docId}" %}
{% api-method-summary %}
Delete User Documents
{% endapi-method-summary %}

{% api-method-description %}
This end point allows you to delete user documents.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="docId" type="string" required=true %}
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



