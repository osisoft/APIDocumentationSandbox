

<h1 id="identity-storage-controllers-api-tenants-roles-roles">Roles</h1>

## Get Tenant Roles

<a id="opIdRoles_Get Tenant Roles"></a>

Get all Roles for a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_get-tenant-roles-parameters">Parameters</h3>

`string tenantId`<br/>Id of tenant.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of providers to skip.<br/><br/>`[optional] integer count`<br/>Max number of providers to return.<br/><br/>

<h3 id="roles_get-tenant-roles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [Role](#schemarole)s|List of Roles found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Tenant Roles Header

<a id="opIdRoles_Get Tenant Roles Header"></a>

Get header for Roles to get the total number of Roles for a given tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_get-tenant-roles-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>

<h3 id="roles_get-tenant-roles-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Post Tenant Role

<a id="opIdRoles_Post Tenant Role"></a>

Create a new `Role` for a Tenant.

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

`string tenantId`<br/>Tenant ID.<br/><br/>

<h3 id="roles_post-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Role](#schemarole)|Role created.|
|302|None|A role with the same Id or Name already exists in the Tenant.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|A role with some matching values already exists in Tenant.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get Tenant Role

<a id="opIdRoles_Get Tenant Role"></a>

Returns the specified Role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_get-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string roleId`<br/>Role Id.<br/><br/>

<h3 id="roles_get-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Role specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role or Tenant not found.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Tenant Role Header

<a id="opIdRoles_Get Tenant Role Header"></a>

Get header for a Role on given tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_get-tenant-role-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of tenant.<br/><br/>`string roleId`<br/>Id of provider.<br/><br/>

<h3 id="roles_get-tenant-role-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Role specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|IdentityProvider or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Put Tenant Role

<a id="opIdRoles_Put Tenant Role"></a>

Update a `Role` for a Tenant.

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

`string tenantId`<br/>Tenant ID.<br/><br/>`string roleId`<br/>Role ID.<br/><br/>

<h3 id="roles_put-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Updated Role.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Role not found.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Delete Tenant Role

<a id="opIdRoles_Delete Tenant Role"></a>

Delete a Role from a Tenant.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_delete-tenant-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant ID.<br/><br/>`string roleId`<br/>Role ID.<br/><br/>

<h3 id="roles_delete-tenant-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
|405|[ErrorResponse](#schemaerrorresponse)|Delete built-in Roles not allowed.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get Client Credential Clients For A Role

<a id="opIdRoles_Get Client Credential Clients For A Role"></a>

Get all the clients for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_get-client-credential-clients-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string roleId`<br/>Role Id.<br/><br/>

<h3 id="roles_get-client-credential-clients-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientCredentialClient](#schemaclientcredentialclient)s|Clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

### Example response body

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Client Credential Clients Count For A Role

<a id="opIdRoles_Get Client Credential Clients Count For A Role"></a>

Get the total number of clients for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_get-client-credential-clients-count-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string roleId`<br/>Role Id.<br/><br/>

<h3 id="roles_get-client-credential-clients-count-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for the total number of clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Users For A Role

<a id="opIdRoles_Get Users For A Role"></a>

Get all the Users for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_get-users-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string roleId`<br/>Role Id.<br/><br/>

<h3 id="roles_get-users-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)s|Users for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

### Example response body

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Users Count For A Role

<a id="opIdRoles_Get Users Count For A Role"></a>

Gets the total number of users for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_get-users-count-for-a-role-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id for the Role.<br/><br/>`string roleId`<br/>Role Id.<br/><br/>

<h3 id="roles_get-users-count-for-a-role-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

# Schemas

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

|Name|Type|Required|Nullable|Description|
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
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}

```

Object returned whenever there is an error.

### Properties

|Name|Type|Required|Nullable|Description|
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

Object for retrieving a User.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets unique User ID.|
|GivenName|string|false|true|Gets or sets given name of user.|
|Surname|string|false|true|Gets or sets surname of user.|
|Name|string|false|true|Gets or sets name of user.|
|Email|string|false|true|Gets or sets email of user.|
|ContactEmail|string|false|true|Gets or sets contact email for user. User will only be contacted through this email.|
|ContactGivenName|string|false|true|Gets or sets preferred contact name for user.|
|ContactSurname|string|false|true|Gets or sets preferred contact surname for user.|
|ExternalUserId|string|false|true|Gets or sets provider id for user. This is the unique ID we get from the Identity Provider.|
|IdentityProviderId|guid|false|true|Gets or sets Identity Provider Id used to authenticate User. Will be set once the User accepts an invitation. If not specified when sending the invitation to the User, it can be any of the Identity Provider Ids configured for this Tenant.|
|RoleIds|List of strings|false|true|Gets or sets list of strings of RoleIds.|

<h2 id="tocS_ClientCredentialClient">ClientCredentialClient</h2>

<a id="schemaclientcredentialclient"></a>
<a id="schema_ClientCredentialClient"></a>
<a id="tocSclientcredentialclient"></a>
<a id="tocsclientcredentialclient"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[Client](#schemaclient)|false|false|Base object used during Client creation.|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleIds|List of strings|false|true|Gets or sets list of Roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning Admin roles to a client.|

<h2 id="tocS_Client">Client</h2>

<a id="schemaclient"></a>
<a id="schema_Client"></a>
<a id="tocSclient"></a>
<a id="tocsclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ]
}

```

Base object used during Client creation.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets client ID for this client. This ID should be a GUID.|
|Name|string|false|true|Gets or sets name of Client.|
|Enabled|boolean|false|true|Gets or sets whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|false|true|Gets or sets lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|List of strings|false|true|Gets or sets for OSIsoft internal use only.|

