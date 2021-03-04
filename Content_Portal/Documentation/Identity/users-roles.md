---
title: Identity/users-roles v20210304.3
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-users-roles-roles">Roles</h1>
APIs for getting, updating, and deleting users roles.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|guid|None|
|Name|string|None|
|Description|string|None|
|RoleScope|[RoleScope](#schemarolescope)|None|
|TenantId|guid|None|
|CommunityId|guid|None|
|RoleTypeId|guid|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

	

	

	

---
## List User Roles

<a id="opIdRoles_List User Roles"></a>

Returns a list of roles for a given user.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

<h3 id="roles_list-user-roles-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of roles to skip.<br/><br/>`[optional] integer count`<br/>Max number of roles to return.<br/><br/>

<h3 id="roles_list-user-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of roles found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or user not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get User Roles Header

<a id="opIdRoles_Get User Roles Header"></a>

Head request to get the total number of user roles for the specified user.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

<h3 id="roles_get-user-roles-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="roles_get-user-roles-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or user not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Put User Roles

<a id="opIdRoles_Put User Roles"></a>

Replaces existing user roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

### Request Body

Update roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

<h3 id="roles_put-user-roles-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="roles_put-user-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 400 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_Role">Role</h2>

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|RoleScope|[RoleScope](#schemarolescope)|false|true|None|
|TenantId|guid|false|true|None|
|CommunityId|guid|false|true|None|
|RoleTypeId|guid|false|true|None|

<h2 id="tocS_RoleScope">RoleScope</h2>

<a id="schemarolescope"></a>
<a id="schema_RoleScope"></a>
<a id="tocSrolescope"></a>
<a id="tocsrolescope"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Account|1|
|Community|2|
|Cluster|3|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}

```

Object returned whenever there is an error.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|

