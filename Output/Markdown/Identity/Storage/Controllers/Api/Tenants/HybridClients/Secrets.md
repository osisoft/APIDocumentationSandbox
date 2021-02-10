

<h1 id="identity-storage-controllers-api-tenants-hybridclients-secrets-secrets">Secrets</h1>

## Get Hybrid Client Secrets

<a id="opIdSecrets_Get Hybrid Client Secrets"></a>

Get all secrets for a Hybrid Client. Total number of secrets in the Client set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_get-hybrid-client-secrets-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="secrets_get-hybrid-client-secrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientSecret](#schemaclientsecret)s|Hybrid Client Secret information found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
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

## Get Hybrid Client Secrets Header

<a id="opIdSecrets_Get Hybrid Client Secrets Header"></a>

Return total number of Secrets in a Hybrid Client. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_get-hybrid-client-secrets-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="secrets_get-hybrid-client-secrets-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Hybrid Client Secret headers.|
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

## Add Hybrid Client Secret

<a id="opIdSecrets_Add Hybrid Client Secret"></a>

Add a new secret to a Client Credential Client. A client can have a maximum of 10 secrets. We advise against creating secrets that do not expire.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

### Request Body

ClientSecretCreateOrUpdate object.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_add-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="secrets_add-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse](#schemaclientsecretresponse)|Hybrid Client Secret created.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0,
  "Secret": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get Hybrid Client Secret

<a id="opIdSecrets_Get Hybrid Client Secret"></a>

Get a Hybrid Client Secret.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>`integer secretId`<br/>Id of Secret.<br/><br/>

<h3 id="secrets_get-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Hybrid Client Secret specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
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

## Get Hybrid Client Secret Header

<a id="opIdSecrets_Get Hybrid Client Secret Header"></a>

Validate that a Secret with given Id exists in the Client. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-hybrid-client-secret-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>`integer secretId`<br/>Id of Secret.<br/><br/>

<h3 id="secrets_get-hybrid-client-secret-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Hybrid Client Secret.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Secret, Client, or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Update Hybrid Client Secret

<a id="opIdSecrets_Update Hybrid Client Secret"></a>

Update a Hybrid Client Secret. It can take up to one hour for the update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

### Request Body

ClientSecretCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_update-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>`integer secretId`<br/>Id of Secret.<br/><br/>

<h3 id="secrets_update-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Hybrid Client Secret updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Delete Hybrid Client Secret

<a id="opIdSecrets_Delete Hybrid Client Secret"></a>

Delete a Secret from a Hybrid Client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued using this Secret will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_delete-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>`integer secretId`<br/>Id of Secret.<br/><br/>

<h3 id="secrets_delete-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
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

## Get V1 Preview Hybrid Client Secrets

<a id="opIdSecrets_Get V1 Preview Hybrid Client Secrets"></a>

Get all secrets for a Hybrid Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_get-v1-preview-hybrid-client-secrets-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="secrets_get-v1-preview-hybrid-client-secrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientSecret2](#schemaclientsecret2)s|Hybrid Client Secrets found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
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

## Add V1 Preview Hybrid Client Secret

<a id="opIdSecrets_Add V1 Preview Hybrid Client Secret"></a>

Add a new secret for a Hybrid Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

### Request Body

Client Secret to create.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_add-v1-preview-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>

<h3 id="secrets_add-v1-preview-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse2](#schemaclientsecretresponse2)|Hybrid Client Secret created.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string",
  "ClientSecret": "string",
  "Secret": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get V1 Preview Hybrid Client Secret

<a id="opIdSecrets_Get V1 Preview Hybrid Client Secret"></a>

Get a specific Hybrid Client Secret.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-v1-preview-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>`integer secretId`<br/>Id of secret.<br/><br/>

<h3 id="secrets_get-v1-preview-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Hybrid Client Secret specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
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

## Update V1 Preview Hybrid Client Secret

<a id="opIdSecrets_Update V1 Preview Hybrid Client Secret"></a>

Update a Hybrid Client Secret Only Secret Description and Secret Expiration Date can be updated.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

### Request Body

Client Secret details.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_update-v1-preview-hybrid-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of client.<br/><br/>`integer secretId`<br/>secretId.<br/><br/>

<h3 id="secrets_update-v1-preview-hybrid-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Updated Hybrid Client Secret.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

# Schemas

<h2 id="tocS_ClientSecret">ClientSecret</h2>

<a id="schemaclientsecret"></a>
<a id="schema_ClientSecret"></a>
<a id="tocSclientsecret"></a>
<a id="tocsclientsecret"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[ClientSecretCreateOrUpdate](#schemaclientsecretcreateorupdate)|false|false|Object to write a Client Secret.|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|int32|false|false|Gets or sets id for this Secret.|

<h2 id="tocS_ClientSecretCreateOrUpdate">ClientSecretCreateOrUpdate</h2>

<a id="schemaclientsecretcreateorupdate"></a>
<a id="schema_ClientSecretCreateOrUpdate"></a>
<a id="tocSclientsecretcreateorupdate"></a>
<a id="tocsclientsecretcreateorupdate"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}

```

Object to write a Client Secret.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|

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

<h2 id="tocS_ClientSecretResponse">ClientSecretResponse</h2>

<a id="schemaclientsecretresponse"></a>
<a id="schema_ClientSecretResponse"></a>
<a id="tocSclientsecretresponse"></a>
<a id="tocsclientsecretresponse"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[ClientSecret](#schemaclientsecret)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Secret|string|false|true|Gets or sets client secret.|

<h2 id="tocS_ClientSecret2">ClientSecret2</h2>

<a id="schemaclientsecret2"></a>
<a id="schema_ClientSecret2"></a>
<a id="tocSclientsecret2"></a>
<a id="tocsclientsecret2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[ClientSecretCreateOrUpdate](#schemaclientsecretcreateorupdate)|false|false|Object to write a Client Secret.|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|SecretId|string|false|true|None|
|Id|string|false|true|None|

<h2 id="tocS_ClientSecretResponse2">ClientSecretResponse2</h2>

<a id="schemaclientsecretresponse2"></a>
<a id="schema_ClientSecretResponse2"></a>
<a id="tocSclientsecretresponse2"></a>
<a id="tocsclientsecretresponse2"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[ClientSecret2](#schemaclientsecret2)|false|false|None|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|ClientSecret|string|false|true|None|
|Secret|string|false|true|None|

