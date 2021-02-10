

<h1 id="identity-storage-controllers-api-tenants-implicitclients-implicitclients">ImplicitClients</h1>

## Get Implicit Clients

<a id="opIdImplicitClients_Get Implicit Clients"></a>

Get all Implicit clients from a Tenant. Optionally, get a list of requested clients. Total number of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_get-implicit-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.<br/><br/>

<h3 id="implicitclients_get-implicit-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ImplicitClient](#schemaimplicitclient)s|Implicit Clients found.|
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
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Get Implicit Clients Header

<a id="opIdImplicitClients_Get Implicit Clients Header"></a>

Return total number of Implicit clients in a Tenant. Optionally, check based on a list of requested clients. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_get-implicit-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count Clients that have these tags.<br/><br/>

<h3 id="implicitclients_get-implicit-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Implicit Client headers found on Tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Create Implicit Client

<a id="opIdImplicitClients_Create Implicit Client"></a>

Create an Implicit Client in a Tenant. No Secret will be generated for this Client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ImplicitClients
```

### Request Body

New ImplicitClient object.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_create-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="implicitclients_create-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ImplicitClient](#schemaimplicitclient)|Implicit Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
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
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get Implicit Client

<a id="opIdImplicitClients_Get Implicit Client"></a>

Get an Implicit Client from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_get-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="implicitclients_get-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit Client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
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
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Get Implicit Client Header

<a id="opIdImplicitClients_Get Implicit Client Header"></a>

Validate that an Implicit Client exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_get-implicit-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="implicitclients_get-implicit-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Implicit Client.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Update Implicit Client

<a id="opIdImplicitClients_Update Implicit Client"></a>

Update an Implicit Client. It can take up to one hour for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

### Request Body

Updated Implicit Client values. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_update-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="implicitclients_update-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit Client updated.|
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
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Delete Implicit Client

<a id="opIdImplicitClients_Delete Implicit Client"></a>

Delete an Implicit Client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_delete-implicit-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="implicitclients_delete-implicit-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
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

## Get V1 Preview Implicit Clients

<a id="opIdImplicitClients_Get V1 Preview Implicit Clients"></a>

Get all Implicit Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_get-v1-preview-implicit-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="implicitclients_get-v1-preview-implicit-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ImplicitClient2](#schemaimplicitclient2)s|Implicit Clients found.|
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
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

# Schemas

<h2 id="tocS_ImplicitClient">ImplicitClient</h2>

<a id="schemaimplicitclient"></a>
<a id="schema_ImplicitClient"></a>
<a id="tocSimplicitclient"></a>
<a id="tocsimplicitclient"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[WebClient](#schemawebclient)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AllowedCorsOrigins|List of strings|false|true|Gets or sets the values used by the default CORS policy service implementations to build a CORS policy for JavaScript clients. Maximum 10 for client.|

<h2 id="tocS_WebClient">WebClient</h2>

<a id="schemawebclient"></a>
<a id="schema_WebClient"></a>
<a id="tocSwebclient"></a>
<a id="tocswebclient"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[Client](#schemaclient)|false|false|Base object used during Client creation.|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RedirectUris|List of strings|false|true|Gets or sets the allowed URIs to which return tokens or authorization codes can be returned. Wildcards are ignored. URIs must match exactly what you are redirecting to after login. If URIs do not match, the authentication process will fail with a bad_client error. Maximum 10 per client.|
|PostLogoutRedirectUris|List of strings|false|true|Gets or sets allowed URIs to redirect to after logout. Wildcards are ignored. URIs must match exactly what you are redirecting to after logout. Maximum 10 for client.|
|ClientUri|string|false|true|Gets or sets URI to a page with information about client (used on consent screen).|
|LogoUri|string|false|true|Gets or sets URI to client logo (used on consent screen).|

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

<h2 id="tocS_ImplicitClient2">ImplicitClient2</h2>

<a id="schemaimplicitclient2"></a>
<a id="schema_ImplicitClient2"></a>
<a id="tocSimplicitclient2"></a>
<a id="tocsimplicitclient2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[WebClient2](#schemawebclient2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AllowedCorsOrigins|List of strings|false|true|None|

<h2 id="tocS_WebClient2">WebClient2</h2>

<a id="schemawebclient2"></a>
<a id="schema_WebClient2"></a>
<a id="tocSwebclient2"></a>
<a id="tocswebclient2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[Client2](#schemaclient2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RedirectUris|List of strings|false|true|None|
|PostLogoutRedirectUris|List of strings|false|true|None|
|ClientUri|string|false|true|None|
|LogoUri|string|false|true|None|

<h2 id="tocS_Client2">Client2</h2>

<a id="schemaclient2"></a>
<a id="schema_Client2"></a>
<a id="tocSclient2"></a>
<a id="tocsclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|ClientId|string|false|true|None|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Enabled|boolean|false|true|None|
|Tags|List of strings|false|true|None|

