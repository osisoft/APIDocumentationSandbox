---
title: Identity/authorization-code-clients v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-authorization-code-clients-authorization-code-clients">Authorization Code Clients</h1>
Authorization code clients are used in JavaScript/Browser (SPA) based applications or native mobile applications with the presence of a user. These clients are issued an unique identifier. Authorization code clients are not issued secrets or refresh tokens. 

Object used during Authorization Code Client creation.

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
|AllowedCorsOrigins|string[]|Values used by the default CORS policy service implementations to build a CORS policy for JavaScript clients.|

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
## List Authorization Code Clients

<a id="opIdAuthorizationCodeClients_List Authorization Code Clients"></a>

Gets all authorization code clients from a tenant. Optionally, get a list of requested clients. Total number of clients in the tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

<h3 id="authorizationcodeclients_list-authorization-code-clients-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of Ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="authorizationcodeclients_list-authorization-code-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AuthorizationCodeClient](#schemaauthorizationcodeclient)[]|Authorization code clients found.|
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
## Get Authorization Code Clients Header

<a id="opIdAuthorizationCodeClients_Get Authorization Code Clients Header"></a>

Returns the total number of authorization code clients in a tenant. Optionally, check based on a list of requested clients. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

<h3 id="authorizationcodeclients_get-authorization-code-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of Ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count clients that have these tags.<br/><br/>

<h3 id="authorizationcodeclients_get-authorization-code-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Authorization code client headers.|
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
## Create Authorization Code Client

<a id="opIdAuthorizationCodeClients_Create Authorization Code Client"></a>

Creates an authorization code client. No secret will be generated for this client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

### Request Body

New AuthorizationCodeClient object.<br/>

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

<h3 id="authorizationcodeclients_create-authorization-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="authorizationcodeclients_create-authorization-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization code client created.|
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
## Get Authorization Code Client

<a id="opIdAuthorizationCodeClients_Get Authorization Code Client"></a>

Gets an authorization code client from tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_get-authorization-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="authorizationcodeclients_get-authorization-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization code client specified.|
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
## Get Authorization Code Client Header

<a id="opIdAuthorizationCodeClients_Get Authorization Code Client Header"></a>

Validates that an authorization code client exists in tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_get-authorization-code-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="authorizationcodeclients_get-authorization-code-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Header for specified authorization code client.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

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
## Update Authorization Code Client

<a id="opIdAuthorizationCodeClients_Update Authorization Code Client"></a>

Updates an authorization code client. It can take up to one hour for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

### Request Body

Updated authorization code client values. Properties that are not set or are null will not be changed.<br/>

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

<h3 id="authorizationcodeclients_update-authorization-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="authorizationcodeclients_update-authorization-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization code client updated.|
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
## Delete Authorization Code Client

<a id="opIdAuthorizationCodeClients_Delete Authorization Code Client"></a>

Deletes an authorization code client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_delete-authorization-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="authorizationcodeclients_delete-authorization-code-client-responses">Responses</h3>

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

# Definitions

<h2 id="tocS_AuthorizationCodeClient">AuthorizationCodeClient</h2>

<a id="schemaauthorizationcodeclient"></a>
<a id="schema_AuthorizationCodeClient"></a>
<a id="tocSauthorizationcodeclient"></a>
<a id="tocsauthorizationcodeclient"></a>

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

Object used during Authorization Code Client creation.

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
|AllowedCorsOrigins|string[]|false|true|Values used by the default CORS policy service implementations to build a CORS policy for JavaScript clients.|

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

