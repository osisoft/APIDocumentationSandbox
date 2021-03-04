---
title: Identity/client-credential-clients-secrets v20210304.5
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-client-credential-clients-secrets-secrets">Secrets</h1>
Secrets are used to authenticate client credential clients. A secret has an expiration date or can be created to never expire. We advise to avoid creating secrets that do not expire. After a secret expires it can no longer be used to authenticate the client. Any access token issued while a secret is still valid will be active until the token itself expires. Safe storage of secrets is your responsibility. OCS does not store secret values, so once lost there is no way to retrieve the value of a secret.

	

	

	

	

	

	

---
## List Client Credential Client Secrets

<a id="opIdSecrets_List Client Credential Client Secrets"></a>

Gets all secrets for a client credential client. Total number of secrets in the client set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_list-client-credential-client-secrets-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="secrets_list-client-credential-client-secrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)[]|List of secret information corresponding to the specified client credential client.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
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
## Get Client Credential Client Secrets Header

<a id="opIdSecrets_Get Client Credential Client Secrets Header"></a>

Returns the total number of secrets in a client credential client. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_get-client-credential-client-secrets-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="secrets_get-client-credential-client-secrets-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Client credential client secret header information.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Add Client Credential Client Secret

<a id="opIdSecrets_Add Client Credential Client Secret"></a>

Adds a new secret to a client credential client. A client can have a maximum of 10 secrets. We advise against creating secrets that do not expire.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
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

<h3 id="secrets_add-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="secrets_add-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse](#schemaclientsecretresponse)|Information about created secret.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "Id": 0,
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Secret": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Client Credential Client Secret

<a id="opIdSecrets_Get Client Credential Client Secret"></a>

Gets a client credential client secret.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>Secret unique identifier.<br/><br/>

<h3 id="secrets_get-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Information about specified secret.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, client, or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Client Credential Client Secret Header

<a id="opIdSecrets_Get Client Credential Client Secret Header"></a>

Validates that a secret with a given unique identifier exists in the client. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-client-credential-client-secret-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>Secret unique identifier.<br/><br/>

<h3 id="secrets_get-client-credential-client-secret-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client secret.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Secret, client, or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update Client Credential Client Secret

<a id="opIdSecrets_Update Client Credential Client Secret"></a>

Updates a client credential client secret. It can take up to one hour for the update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
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

<h3 id="secrets_update-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>Secret unique identifier.<br/><br/>

<h3 id="secrets_update-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Information about updated secret.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, client, or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete Client Credential Client Secret

<a id="opIdSecrets_Delete Client Credential Client Secret"></a>

Deletes a secret from a client credential client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued using this secret will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_delete-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>Secret unique identifier.<br/><br/>

<h3 id="secrets_delete-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, client, or tenant not found.|
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
## List V1 Preview Client Credential Client Secrets

<a id="opIdSecrets_List V1 Preview Client Credential Client Secrets"></a>

Get all secrets for a client credential client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_list-v1-preview-client-credential-client-secrets-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="secrets_list-v1-preview-client-credential-client-secrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)[]|Client credential client secrets found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
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
## Add V1 Preview Client Credential Client Secret

<a id="opIdSecrets_Add V1 Preview Client Credential Client Secret"></a>

Add a new secret for a client credential client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

### Request Body

Client secret to create.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_add-v1-preview-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="secrets_add-v1-preview-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse2](#schemaclientsecretresponse2)|Client credential client secret created.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "SecretId": "string",
  "Id": "string",
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "ClientSecret": "string",
  "Secret": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get V1 Preview Client Credential Client Secret

<a id="opIdSecrets_Get V1 Preview Client Credential Client Secret"></a>

Get a specific client credential client secret.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_get-v1-preview-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>Secret unique identifier.<br/><br/>

<h3 id="secrets_get-v1-preview-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Client credential client secret specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, client, or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update V1 Preview Client Credential Client Secret

<a id="opIdSecrets_Update V1 Preview Client Credential Client Secret"></a>

Update a client credential client secret. Only secret description and secret expiration date can be updated.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

### Request Body

Client secret details.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_update-v1-preview-client-credential-client-secret-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>`integer secretId`<br/>secretId.<br/><br/>

<h3 id="secrets_update-v1-preview-client-credential-client-secret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Updated client credential client secret.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, client, or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_ClientSecret">ClientSecret</h2>

<a id="schemaclientsecret"></a>
<a id="schema_ClientSecret"></a>
<a id="tocSclientsecret"></a>
<a id="tocsclientsecret"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
}

```

Client Secret Object.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|
|Id|int32|false|false|Gets or sets id for this Secret.|

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

<h2 id="tocS_ClientSecretResponse">ClientSecretResponse</h2>

<a id="schemaclientsecretresponse"></a>
<a id="schema_ClientSecretResponse"></a>
<a id="tocSclientsecretresponse"></a>
<a id="tocsclientsecretresponse"></a>

```json
{
  "Id": 0,
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Secret": "string"
}

```

Object returned after a Client Secret is created.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|int32|false|false|Gets or sets id for this Secret.|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|
|Secret|string|false|true|Gets or sets client secret.|

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

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|

<h2 id="tocS_ClientSecret2">ClientSecret2</h2>

<a id="schemaclientsecret2"></a>
<a id="schema_ClientSecret2"></a>
<a id="tocSclientsecret2"></a>
<a id="tocsclientsecret2"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|
|SecretId|string|false|true|None|
|Id|string|false|true|None|

<h2 id="tocS_ClientSecretResponse2">ClientSecretResponse2</h2>

<a id="schemaclientsecretresponse2"></a>
<a id="schema_ClientSecretResponse2"></a>
<a id="tocSclientsecretresponse2"></a>
<a id="tocsclientsecretresponse2"></a>

```json
{
  "SecretId": "string",
  "Id": "string",
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "ClientSecret": "string",
  "Secret": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|SecretId|string|false|true|None|
|Id|string|false|true|None|
|Expiration|date-time|false|true|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean|false|true|Gets or sets determines if the secret expires. Defaults to true. If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced. If Expires is set to true (or null) and Expiration is null, a 400 error will be returned. If Expires is set to false and Expiration is not null, a 400 error will be returned. If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string|false|true|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying secrets easier.|
|ClientSecret|string|false|true|None|
|Secret|string|false|true|None|

