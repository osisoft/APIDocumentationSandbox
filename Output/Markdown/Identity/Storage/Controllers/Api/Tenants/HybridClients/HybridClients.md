

<h1 id="identity-storage-controllers-api-tenants-hybridclients-hybridclients-hybridclients">HybridClients</h1>

## Get Hybrid Clients

<a id="opIdHybridClients_Get Hybrid Clients"></a>

Get a list of Hybrid clients from a Tenant. Optionally, get a list of requested clients. Total number of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_get-hybrid-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of Hybrid Client Ids. Empty, whitespace or null Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.<br/><br/>

<h3 id="hybridclients_get-hybrid-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [HybridClient](#schemahybridclient)s|Hybrid Clients found.|
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

## Get Hybrid Clients Header

<a id="opIdHybridClients_Get Hybrid Clients Header"></a>

Return total number of Hybrid clients in a Tenant. Optionally, check based on a list of requested clients. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_get-hybrid-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of Hybrid Client Ids. Empty, whitespace or null Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count clients that have these tags.<br/><br/>

<h3 id="hybridclients_get-hybrid-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Hybrid Client Secrets found.|
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

## Create Hybrid Client

<a id="opIdHybridClients_Create Hybrid Client"></a>

Create a Hybrid Client. A Client Id and Client Secret will be generated to perform authentication. Make sure to store the Secret somewhere safe as we do not store the actual value after the creation step. If you do not have access to the Secret value, we suggest deleting the Secret and adding a new one for this Client. Clients have unique ids in a Tenant. Currently there is a limit of 50000 clients (of all types) per Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/HybridClients
```

### Request Body

HybridClientCreate object.<br/>

```json
{
  "Id": null,
  "Name": null,
  "Enabled": null,
  "AccessTokenLifetime": null,
  "Tags": null,
  "RedirectUris": null,
  "PostLogoutRedirectUris": null,
  "ClientUri": null,
  "LogoUri": null,
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="hybridclients_create-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="hybridclients_create-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[HybridClientCreateResponse](#schemahybridclientcreateresponse)|Hybrid Client created.|
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
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
    "Id": null,
    "Name": null,
    "Enabled": null,
    "AccessTokenLifetime": null,
    "Tags": null,
    "RedirectUris": null,
    "PostLogoutRedirectUris": null,
    "ClientUri": null,
    "LogoUri": null,
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get Hybrid Client

<a id="opIdHybridClients_Get Hybrid Client"></a>

Get a Hybrid Client from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_get-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="hybridclients_get-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient](#schemahybridclient)|Hybrid Client specified.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
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

## Get Hybrid Client Header

<a id="opIdHybridClients_Get Hybrid Client Header"></a>

Validate that a Hybrid Client exists. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_get-hybrid-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="hybridclients_get-hybrid-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Hybrid Client.|
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

## Update Hybrid Client

<a id="opIdHybridClients_Update Hybrid Client"></a>

Update a Hybrid Client. It can take up to one hour for these values to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

### Request Body

HybridClient object. Properties that are not set or are null will not be changed.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

<h3 id="hybridclients_update-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="hybridclients_update-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient](#schemahybridclient)|Hybrid Client updated.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Delete Hybrid Client

<a id="opIdHybridClients_Delete Hybrid Client"></a>

Delete a Hybrid Client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this Client will be valid until their expiration. Refresh tokens issued to this will be valid up to one hour after deletion.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_delete-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="hybridclients_delete-hybrid-client-responses">Responses</h3>

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

## Get V1 Preview Hybrid Clients

<a id="opIdHybridClients_Get V1 Preview Hybrid Clients"></a>

Get all Hybrid Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_get-v1-preview-hybrid-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="hybridclients_get-v1-preview-hybrid-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [HybridClient2](#schemahybridclient2)s|List of Hybrid Clients found.|
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

## Create V1 Preview Hybrid Client

<a id="opIdHybridClients_Create V1 Preview Hybrid Client"></a>

Create a Hybrid flow Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/HybridClients
```

### Request Body

New HybridClientCreate object.<br/>

```json
{
  "ClientId": null,
  "Id": null,
  "Name": null,
  "Enabled": null,
  "Tags": null,
  "RedirectUris": null,
  "PostLogoutRedirectUris": null,
  "ClientUri": null,
  "LogoUri": null,
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="hybridclients_create-v1-preview-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="hybridclients_create-v1-preview-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[HybridClientResponse](#schemahybridclientresponse)|Hybrid Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Client Limit exceeded.|
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
  "ClientId": null,
  "Id": null,
  "Name": null,
  "Enabled": null,
  "Tags": null,
  "RedirectUris": null,
  "PostLogoutRedirectUris": null,
  "ClientUri": null,
  "LogoUri": null,
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "ClientSecret": "string",
  "SecretId": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get V1 Preview Hybrid Client

<a id="opIdHybridClients_Get V1 Preview Hybrid Client"></a>

Get a Hybrid Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_get-v1-preview-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="hybridclients_get-v1-preview-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient2](#schemahybridclient2)|Hybrid Client specified.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
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

## Update V1 Preview Hybrid Client

<a id="opIdHybridClients_Update V1 Preview Hybrid Client"></a>

Update a Hybrid Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}
```

### Request Body

Updated Hybrid Client values.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

<h3 id="hybridclients_update-v1-preview-hybrid-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="hybridclients_update-v1-preview-hybrid-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient2](#schemahybridclient2)|Updated Hybrid Client.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

# Schemas

<h2 id="tocS_HybridClientCreateResponse">HybridClientCreateResponse</h2>

<a id="schemahybridclientcreateresponse"></a>
<a id="schema_HybridClientCreateResponse"></a>
<a id="tocShybridclientcreateresponse"></a>
<a id="tocshybridclientcreateresponse"></a>

```json
{
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
    "Id": null,
    "Name": null,
    "Enabled": null,
    "AccessTokenLifetime": null,
    "Tags": null,
    "RedirectUris": null,
    "PostLogoutRedirectUris": null,
    "ClientUri": null,
    "LogoUri": null,
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
}

```

Secret information returned after a Hybrid Client is created.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Secret|string|false|true|Gets or sets client secret.|
|Id|int32|false|false|Gets or sets secret Id.|
|Description|string|false|true|Gets or sets description for the initial secret for the client.|
|ExpirationDate|date-time|false|true|Gets or sets expiration date for the initial secret for the client.|
|Client|[HybridClient](#schemahybridclient)|false|true|Gets or sets Hybrid Client object created.|

<h2 id="tocS_HybridClient">HybridClient</h2>

<a id="schemahybridclient"></a>
<a id="schema_HybridClient"></a>
<a id="tocShybridclient"></a>
<a id="tocshybridclient"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[WebClient](#schemawebclient)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AllowOfflineAccess|boolean|false|true|Gets or sets whether this client can request refresh tokens, by providing the *offline_access* scope.|
|AllowAccessTokensViaBrowser|boolean|false|true|Gets or sets whether this HybridClient is allowed to receive access tokens via the browser. This is useful to harden flows that allow multiple response types (e.g. by disallowing a hybrid flow client that is supposed to use code *id_token* to add the *token* response type, thus leaking the token to the browser).|

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

<h2 id="tocS_HybridClientCreate">HybridClientCreate</h2>

<a id="schemahybridclientcreate"></a>
<a id="schema_HybridClientCreate"></a>
<a id="tocShybridclientcreate"></a>
<a id="tocshybridclientcreate"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[HybridClient](#schemahybridclient)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|SecretDescription|string|false|true|Gets or sets description for the initial secret for the client.|
|SecretExpirationDate|date-time|false|true|Gets or sets expiration date for the initial secret for the client. If set to null the secret will never expire. We advise against such practice.|

<h2 id="tocS_HybridClientResponse">HybridClientResponse</h2>

<a id="schemahybridclientresponse"></a>
<a id="schema_HybridClientResponse"></a>
<a id="tocShybridclientresponse"></a>
<a id="tocshybridclientresponse"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[HybridClientCreate2](#schemahybridclientcreate2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|ClientSecret|string|false|true|None|
|SecretId|string|false|true|None|

<h2 id="tocS_HybridClientCreate2">HybridClientCreate2</h2>

<a id="schemahybridclientcreate2"></a>
<a id="schema_HybridClientCreate2"></a>
<a id="tocShybridclientcreate2"></a>
<a id="tocshybridclientcreate2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[HybridClient2](#schemahybridclient2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|SecretDescription|string|false|true|None|
|SecretExpirationDate|date-time|false|true|None|

<h2 id="tocS_HybridClient2">HybridClient2</h2>

<a id="schemahybridclient2"></a>
<a id="schema_HybridClient2"></a>
<a id="tocShybridclient2"></a>
<a id="tocshybridclient2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[WebClient2](#schemawebclient2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AllowOfflineAccess|boolean|false|true|None|
|AllowAccessTokensViaBrowser|boolean|false|true|None|

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

