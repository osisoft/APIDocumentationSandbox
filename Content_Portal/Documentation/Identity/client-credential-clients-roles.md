---
title: Identity/client-credential-clients-roles v20210407.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Roles
APIs for getting, updating, and deleting client credential client roles.

## List Roles for Client Credential Client All

<a id="opIdRoles_List Roles for Client Credential Client All"></a>

Returns a list of roles for the specified client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles
?query={query}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of roles to skip.<br/><br/>`[optional] integer count`
<br/>Max number of roles to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Get Roles for Client Credential Client Header (` Client Credential Clients` path)

<a id="opIdRoles_Get Roles for Client Credential Client Header (` Client Credential Clients` path)"></a>

Head request to get the total number of client credential client roles for the specified client credential client.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Replace Client Credential Client's Roles All

<a id="opIdRoles_Replace Client Credential Client's Roles All"></a>

Replaces existing client credential client roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Request Body

Update roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of updated client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## List Roles for Client Credential Client

<a id="opIdRoles_List Roles for Client Credential Client"></a>

Returns a list of roles for the specified client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles
?query={query}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of roles to skip.<br/><br/>`[optional] integer count`
<br/>Max number of roles to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or client credential client not found.|
|408|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Get Roles for Client Credential Client Header (` Clients` path)

<a id="opIdRoles_Get Roles for Client Credential Client Header (` Clients` path)"></a>

Head request to get the total number of client credential client roles for the specified client credential client.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client roles.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or client credential client not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---

## Replace Client Credential Client's Roles

<a id="opIdRoles_Replace Client Credential Client's Roles"></a>

Replaces existing client credential client roles.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Clients/{clientId}/Roles
```

#### Parameters

`string tenantId`
<br/>Tenant unique identifier.<br/><br/>`string clientId`
<br/>Client credential client unique identifier.<br/><br/>

### Request Body

Update roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of updated client credential client roles.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client credential client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 0,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## Role

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

Object for retrieving a role.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Role unique identifier. Generated by the server upon creation.|
|Name|string|false|true|Role name. This cannot be empty.|
|Description|string|false|true|Role description.|
|RoleScope|[RoleScope](#schemarolescope)|false|true|Role scope.|
|TenantId|string|false|true|Tenant unique identifier, if this is a Tenant Role. Otherwise set to null.|
|CommunityId|string|false|true|Community unique identifier, if this is a Community Role. Otherwise set to null.|
|RoleTypeId|string|false|true|Role type identifier for built-in roles.|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 0,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}

```

---

## RoleScope

<a id="schemarolescope"></a>
<a id="schema_RoleScope"></a>
<a id="tocSrolescope"></a>
<a id="tocsrolescope"></a>

Role Scopes.

#### Enumerated Values

|Property|Value|
|---|---|
|None|0|
|Tenant|1|
|Community|2|
|Cluster|3|

---

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|

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

---

