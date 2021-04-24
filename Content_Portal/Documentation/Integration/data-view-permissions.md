---
title: Integration/data-view-permissions v20210423.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Data View Permissions
This portion of the [overall data views API](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/DataViewsAPIOverview/Data_Views_API_Overview.html) focuses on [securing data views](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/SecureDataViews/Securing_Data_Views.html) by setting their ownership and permissions.<br/>

## Get Data View Access Control List

<a id="opIdDataViewPermissions_Get Data View Access Control List"></a>

Gets the default [`AccessControlList`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#access-control-lists) for the DataViews collection.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The access control list of the requested data view<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized to view the requested data view's access control list<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The requested data view was not found<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
{
  "RoleTrusteeAccessControlEntries": 
  [
    {
      "Trustee": {
        "Type": Role,
        "RoleId": "11111111-1111-1111-1111-111111111111"
      },
      "AccessType": Allowed,
      "AccessRights": 1
    },
    {
      "Trustee": {
        "Type": Role,
        "RoleId": "22222222-2222-2222-2222-222222222222"
      },
      "AccessType": Allowed,
      "AccessRights": 15
    },
    {
      "Trustee": {
        "Type": User,
        "RoleId": "33333333-3333-3333-3333-333333333333"
      },
      "AccessType": Denied,
      "AccessRights": 8
    }
  ]
}
```
> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---

## Update Data View Access Control List

<a id="opIdDataViewPermissions_Update Data View Access Control List"></a>

Updates the default [`AccessControlList`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#access-control-lists) for the DataViews collection.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

An [`AccessControlList`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#access-control-lists)<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Successfully updated the data view access control list<br/>|
|400|[ErrorResponse](#schemaerrorresponse)|The request is not valid. See the response body for details<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized to update the requested data view's access control list<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The requested data view was not found<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---

## List Data View Access Rights

<a id="opIdDataViewPermissions_List Data View Access Rights"></a>

Gets the access rights to the requested data view for the calling user or client.<br/>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accessrights
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A list of access rights to the requested data view<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized for this operation<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The requested data view was not found<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
[
  "Read",
  "Write",
  "Delete",
  "ManageAccessControl"
]
```
> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---

## Get Data View Owner

<a id="opIdDataViewPermissions_Get Data View Owner"></a>

Gets the owner [`Trustee`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#owner) of the specified data view.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The owner of the requested data view<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized to view the requested data view's owner<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The requested data view was not found<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
{
    "Type": User,
    "TenantId": "55555555-5555-5555-5555-555555555555",
    "ObjectId": "44444444-4444-4444-4444-444444444444"
}
```
> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---

## Update Data View Owner

<a id="opIdDataViewPermissions_Update Data View Owner"></a>

Updates the owner [`Trustee`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#owner) of the specified data view.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

A [`Trustee`](https://ocs-docs.osisoft.com/Content_Portal/Documentation/Access_Control.html#owner)<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Successfully updated the data view owner<br/>|
|400|[ErrorResponse](#schemaerrorresponse)|The request is not valid. See the response body for details<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized to update the requested data view's owner<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The requested data view was not found<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---
# Definitions

## AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}

```

---

## AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Trustee|[Trustee](#schematrustee)|false|true|None|
|AccessType|[AccessType](#schemaaccesstype)|false|false|None|
|AccessRights|int64|false|false|None|

```json
{
  "Trustee": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessType": 0,
  "AccessRights": 0
}

```

---

## Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[TrusteeType](#schematrusteetype)|false|false|None|
|ObjectId|string|false|true|None|
|TenantId|string|false|true|None|

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}

```

---

## TrusteeType

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

---

## AccessType

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

---

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|
|ChildErrors|object|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}

```

---

