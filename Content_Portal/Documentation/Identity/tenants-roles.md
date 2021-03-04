---
title: Identity/tenants-roles v20210304.5
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-tenants-roles-roles">Roles</h1>
APIs for creating, getting, updating, and deleting roles on a tenant.

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
## List Tenant Roles

<a id="opIdRoles_List Tenant Roles"></a>

Gets all roles for a tenant including roles for any communities that the tenant belongs to.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_list-tenant-roles-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of providers to skip.<br/><br/>`[optional] integer count`<br/>Max number of providers to return.<br/><br/>

<h3 id="roles_list-tenant-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)[]|List of roles found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 401 Response

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
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Roles Header

<a id="opIdRoles_Get Tenant Roles Header"></a>

Gets header for roles to get the total number of roles for a given tenant including community roles for any community the tenant is joined to.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_get-tenant-roles-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="roles_get-tenant-roles-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Post Tenant Role

<a id="opIdRoles_Post Tenant Role"></a>

Creates a new tenant `Role`.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Roles
```

### Request Body

Role to create.<br/>

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

<h3 id="roles_post-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="roles_post-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Role](#schemarole)|Role created.|
|302|None|A role with the same unique identifier or name already exists in the tenant.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|A role with some matching values already exists in tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Role

<a id="opIdRoles_Get Tenant Role"></a>

Returns the specified role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_get-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_get-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Role specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role or tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Role Header

<a id="opIdRoles_Get Tenant Role Header"></a>

Gets header for a role on given tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_get-tenant-role-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Provider unique identifier.<br/><br/>

<h3 id="roles_get-tenant-role-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for role specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Put Tenant Role

<a id="opIdRoles_Put Tenant Role"></a>

Updates a `Role` for a tenant.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

### Request Body

Role to update.<br/>

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

<h3 id="roles_put-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_put-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Updated role.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete Tenant Role

<a id="opIdRoles_Delete Tenant Role"></a>

Deletes any tenant-scoped, non built-in `Role` by its role unique identifier.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_delete-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_delete-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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

---
## List Client Credential Clients For A Role

<a id="opIdRoles_List Client Credential Clients For A Role"></a>

Gets all the clients for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_list-client-credential-clients-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_list-client-credential-clients-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)[]|Clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or role not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Client Credential Clients Count For A Role

<a id="opIdRoles_Get Client Credential Clients Count For A Role"></a>

Gets the total number of clients for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_get-client-credential-clients-count-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_get-client-credential-clients-count-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for the total number of clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or role not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## List Users For A Role

<a id="opIdRoles_List Users For A Role"></a>

Gets all the users for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_list-users-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_list-users-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)[]|Users for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or role not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Users Count For A Role

<a id="opIdRoles_Get Users Count For A Role"></a>

Gets the total number of users for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_get-users-count-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string roleId`<br/>Role unique identifier.<br/><br/>

<h3 id="roles_get-users-count-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or role not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
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

<h2 id="tocS_User">User</h2>

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object for retrieving a user.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|User unique identifier.|
|GivenName|string|false|true|Given name of the user.|
|Surname|string|false|true|Surname of the user.|
|Name|string|false|true|Name of the user.|
|Email|string|false|true|Email of the user.|
|ContactEmail|string|false|true|Contact email for the user. User will only be contacted through this email.|
|ContactGivenName|string|false|true|Preferred contact name for the user.|
|ContactSurname|string|false|true|Preferred contact surname for the user.|
|ExternalUserId|string|false|true|Provider unique identifier for the user. This is the unique identifier we get from the identity provider.|
|IdentityProviderId|guid|false|true|Identity provider unique identifier used to authenticate the user. Will be set once the user accepts an invitation. If not specified when sending the invitation to the user, it can be any of the identity provider Ids configured for this tenant.|
|RoleIds|string[]|false|true|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

<h2 id="tocS_ClientCredentialClient">ClientCredentialClient</h2>

<a id="schemaclientcredentialclient"></a>
<a id="schema_ClientCredentialClient"></a>
<a id="tocSclientcredentialclient"></a>
<a id="tocsclientcredentialclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}

```

Object to get or update a client credential client.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|false|true|Name of client.|
|Enabled|boolean|false|true|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|false|true|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|false|true|Tags for OSIsoft internal use only.|
|RoleIds|string[]|false|true|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

