---
title: Identity/implicit-clients v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-implicit-clients-implicit-clients">Implicit Clients</h1>
Implicit client has been deprecated. We suggest using an authorization code client instead of an implicit client. Implicit clients are used in JavaScript/Browser (SPA) based applications or native mobile applications with the presence of a user. These clients are not issued secrets or refresh tokens.

Object used during implicit client creation.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|RedirectUris|string[]|Allowed URIs to which return tokens or authorization codes can be returned. Wildcards are ignored. URIs must match exactly what you are redirecting to after login. If URIs do not match, the authentication process will fail with a bad_client error. Maximum 10 per client.|
|PostLogoutRedirectUris|string[]|Allowed URIs to redirect to after logout. Wildcards are ignored. URIs must match exactly what you are redirecting to after logout. Maximum 10 per client.|
|ClientUri|string|URI to a page with information about client (used on consent screen).|
|LogoUri|string|URI to client logo (used on consent screen).|
|Id|string|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|Name of client.|
|Enabled|boolean|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|Tags for OSIsoft internal use only.|
|AllowedCorsOrigins|string[]|Values used by the default CORS policy service implementations to build a CORS policy for JavaScript clients. Maximum 10 per client.|

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

	

	

	

---
## List Implicit Clients

<a id="opIdImplicitClients_List Implicit Clients"></a>

Gets all implicit clients from a tenant. Optionally, get a list of requested clients. Total number of clients in the tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_list-implicit-clients-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of Ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.<br/><br/>

<h3 id="implicitclients_list-implicit-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)[]|Implicit clients found.|
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
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Implicit Clients Header

<a id="opIdImplicitClients_Get Implicit Clients Header"></a>

Returns the total number of implicit clients in a tenant. Optionally, check based on a list of requested clients. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_get-implicit-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of Ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count clients that have these tags.<br/><br/>

<h3 id="implicitclients_get-implicit-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Implicit client headers found on tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or tenant not found.|
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
## Create Implicit Client

<a id="opIdImplicitClients_Create Implicit Client"></a>

Creates an implicit client in a tenant. No secret will be generated for this client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ImplicitClients
```

### Request Body

New ImplicitClient object.<br/>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_create-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="implicitclients_create-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ImplicitClient](#schemaimplicitclient)|Implicit client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Client unique identifier already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Implicit Client

<a id="opIdImplicitClients_Get Implicit Client"></a>

Gets an implicit client from a tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_get-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="implicitclients_get-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
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
## Get Implicit Client Header

<a id="opIdImplicitClients_Get Implicit Client Header"></a>

Validates that an implicit client exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_get-implicit-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="implicitclients_get-implicit-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for implicit client.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or tenant not found.|
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
## Update Implicit Client

<a id="opIdImplicitClients_Update Implicit Client"></a>

Updates an implicit client. It can take up to one hour for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

### Request Body

Updated implicit client values. Properties that are not set or are null will not be changed.<br/>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_update-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="implicitclients_update-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit client updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete Implicit Client

<a id="opIdImplicitClients_Delete Implicit Client"></a>

Deletes an implicit client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_delete-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="implicitclients_delete-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
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
<li>Tenant Administrator</li>
</ul>

---
## List V1 Preview Implicit Clients

<a id="opIdImplicitClients_List V1 Preview Implicit Clients"></a>

Get all Implicit Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_list-v1-preview-implicit-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="implicitclients_list-v1-preview-implicit-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient2](#schemaimplicitclient2)[]|Implicit Clients found.|
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
<li>Tenant Administrator</li>
</ul>

---
## Create V1 Preview Implicit Client

<a id="opIdImplicitClients_Create V1 Preview Implicit Client"></a>

Create an Implicit flow Clients.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ImplicitClients
```

### Request Body

New ImplicitClient object.<br/>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_create-v1-preview-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="implicitclients_create-v1-preview-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ImplicitClient2](#schemaimplicitclient2)|Implicit Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Client Id already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get V1 Preview Implicit Client

<a id="opIdImplicitClients_Get V1 Preview Implicit Client"></a>

Get an Implicit Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_get-v1-preview-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="implicitclients_get-v1-preview-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient2](#schemaimplicitclient2)|Implicit Client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update V1 Preview Implicit Client

<a id="opIdImplicitClients_Update V1 Preview Implicit Client"></a>

Update an Implicit Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ImplicitClients/{clientId}
```

### Request Body

Updated Implicit Client values.<br/>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_update-v1-preview-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="implicitclients_update-v1-preview-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient2](#schemaimplicitclient2)|Updated Implicit Client.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_ImplicitClient">ImplicitClient</h2>

<a id="schemaimplicitclient"></a>
<a id="schema_ImplicitClient"></a>
<a id="tocSimplicitclient"></a>
<a id="tocsimplicitclient"></a>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}

```

Object used during implicit client creation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RedirectUris|string[]|false|true|Allowed URIs to which return tokens or authorization codes can be returned. Wildcards are ignored. URIs must match exactly what you are redirecting to after login. If URIs do not match, the authentication process will fail with a bad_client error. Maximum 10 per client.|
|PostLogoutRedirectUris|string[]|false|true|Allowed URIs to redirect to after logout. Wildcards are ignored. URIs must match exactly what you are redirecting to after logout. Maximum 10 per client.|
|ClientUri|string|false|true|URI to a page with information about client (used on consent screen).|
|LogoUri|string|false|true|URI to client logo (used on consent screen).|
|Id|string|false|true|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|false|true|Name of client.|
|Enabled|boolean|false|true|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|false|true|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|false|true|Tags for OSIsoft internal use only.|
|AllowedCorsOrigins|string[]|false|true|Values used by the default CORS policy service implementations to build a CORS policy for JavaScript clients. Maximum 10 per client.|

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
|OperationId|string|true|false|Operation unique identifier of action that caused the error.|
|Error|string|true|false|Error description.|
|Reason|string|true|false|Reason for the error.|
|Resolution|string|true|false|Resolution needed to resolve the Error.|

<h2 id="tocS_ImplicitClient2">ImplicitClient2</h2>

<a id="schemaimplicitclient2"></a>
<a id="schema_ImplicitClient2"></a>
<a id="tocSimplicitclient2"></a>
<a id="tocsimplicitclient2"></a>

```json
{
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "AllowedCorsOrigins": [
    "string"
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RedirectUris|string[]|false|true|None|
|PostLogoutRedirectUris|string[]|false|true|None|
|ClientUri|string|false|true|None|
|LogoUri|string|false|true|None|
|ClientId|string|false|true|None|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Enabled|boolean|false|true|None|
|Tags|string[]|false|true|None|
|AllowedCorsOrigins|string[]|false|true|None|

