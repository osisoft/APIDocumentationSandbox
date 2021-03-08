---
title: Identity/tenants-client-credential-clients v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-tenants-client-credential-clients-client-credential-clients">Client Credential Clients</h1>
Client credential clients are used for machine-to-machine communication without the presence of a user. These clients are issued an unique identifier and secret upon creation, which are later used for authentication against OCS. More than one secret can be created for a client. Because they access resources on OCS and are not associated to users, these clients can be assigned any of the roles in the tenant. We suggest following a least privilege strategy when assigning roles to these clients, as they are more likely to operate in remote machines with a wider attack surface.

	

Object to get or update a client credential client.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|string|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|Name of client.|
|Enabled|boolean|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|Tags for OSIsoft internal use only.|
|RoleIds|string[]|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

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

	

	

	

	

	

	

	

	

	

---
## List Client Credential Clients

<a id="opIdClientCredentialClients_List Client Credential Clients"></a>

Gets a list of client credential clients from a tenant. Optionally, get a list of requested clients. Total number of client credential clients in the tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_list-client-credential-clients-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of client credential client Ids. Empty, whitespace or null Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.<br/><br/>

<h3 id="clientcredentialclients_list-client-credential-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)[]|Client credential clients found.|
|207|[ClientCredentialClientMultiStatusResponse](#schemaclientcredentialclientmultistatusresponse)|Client credential clients found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 207 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
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
  ]
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
## Get Client Credential Clients Header

<a id="opIdClientCredentialClients_Get Client Credential Clients Header"></a>

Returns the total number of client credential clients in a tenant. Optionally, check based on a list of requested client Ids. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_get-client-credential-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of client credential client Ids. Empty, whitespace or null Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count clients that have these tags.<br/><br/>

<h3 id="clientcredentialclients_get-client-credential-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Client credential client headers found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or tenant not found.|
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
## Create Client Credential Client

<a id="opIdClientCredentialClients_Create Client Credential Client"></a>

Creates a client credential client. A client unique identifier and client Secret will be generated to perform authentication. Make sure to store the secret somewhere safe as we do not store the actual value after the creation step. If you do not have access to the secret value, we suggest deleting the secret and adding a new one for this client. Clients have unique Ids in a tenant. Currently there is a limit of 50000 clients (of any type) per tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

### Request Body

ClientCredentialClientCreate object.<br/>

```json
{
  "RoleIds": [
    "string"
  ],
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="clientcredentialclients_create-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="clientcredentialclients_create-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClientCreateResponse](#schemaclientcredentialclientcreateresponse)|Client credential client details for created client.|
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
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Client Credential Client

<a id="opIdClientCredentialClients_Get Client Credential Client"></a>

Gets a client credential client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_get-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_get-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Client credential client details for specified client.|
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
## Get Client Credential Client Header

<a id="opIdClientCredentialClients_Get Client Credential Client Header"></a>

Validates that a client credential client exists. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_get-client-credential-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_get-client-credential-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified client credential client.|
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
## Update Client Credential Client

<a id="opIdClientCredentialClients_Update Client Credential Client"></a>

Updates a client credential client. It can take up to one hour for these values to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

### Request Body

ClientCredentialClient object. Properties that are not set or are null will not be changed.<br/>

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

<h3 id="clientcredentialclients_update-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_update-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Client credential client details for updated client.|
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
<li>Tenant Administrator</li>
</ul>

---
## Delete Client Credential Client

<a id="opIdClientCredentialClients_Delete Client Credential Client"></a>

Deletes a client credential client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_delete-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_delete-client-credential-client-responses">Responses</h3>

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
## List V1 Preview Client Credential Clients

<a id="opIdClientCredentialClients_List V1 Preview Client Credential Clients"></a>

Get all client credential clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_list-v1-preview-client-credential-clients-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array tag`<br/>Only return clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="clientcredentialclients_list-v1-preview-client-credential-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient2](#schemaclientcredentialclient2)[]|List of client credential clients found.|
|207|[ClientCredentialClientMultiStatusResponse2](#schemaclientcredentialclientmultistatusresponse2)|List of client credential clients found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 207 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "ClientId": "string",
      "Id": "string",
      "Name": "string",
      "Enabled": true,
      "Tags": [
        "string"
      ],
      "RoleIds": [
        "string"
      ]
    }
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Create V1 Preview Client Credential Client

<a id="opIdClientCredentialClients_Create V1 Preview Client Credential Client"></a>

Create a client credential flow client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients
```

### Request Body

New ClientCredentialClientCreate object.<br/>

```json
{
  "RoleIds": [
    "string"
  ],
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="clientcredentialclients_create-v1-preview-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="clientcredentialclients_create-v1-preview-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClientResponse](#schemaclientcredentialclientresponse)|Hybrid client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|409|[ErrorResponse](#schemaerrorresponse)|Client unique identifier already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "RoleIds": [
    "string"
  ],
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "ClientSecret": "string",
  "SecretId": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get V1 Preview Client Credential Client

<a id="opIdClientCredentialClients_Get V1 Preview Client Credential Client"></a>

Get a client credential client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_get-v1-preview-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_get-v1-preview-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient2](#schemaclientcredentialclient2)|Client credential client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or tenant not found.|
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
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Update V1 Preview Client Credential Client

<a id="opIdClientCredentialClients_Update V1 Preview Client Credential Client"></a>

Update a client credential client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

### Request Body

Updated client credential client values.<br/>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="clientcredentialclients_update-v1-preview-client-credential-client-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string clientId`<br/>Client unique identifier.<br/><br/>

<h3 id="clientcredentialclients_update-v1-preview-client-credential-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient2](#schemaclientcredentialclient2)|Updated client credential client.|
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
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
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
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_ClientCredentialClientCreateResponse">ClientCredentialClientCreateResponse</h2>

<a id="schemaclientcredentialclientcreateresponse"></a>
<a id="schema_ClientCredentialClientCreateResponse"></a>
<a id="tocSclientcredentialclientcreateresponse"></a>
<a id="tocsclientcredentialclientcreateresponse"></a>

```json
{
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
}

```

Secret information returned after a client credential client is created.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Secret|string|false|true|Client secret.|
|Id|int32|false|false|Secret unique identifier.|
|Description|string|false|true|Description for the initial secret for the client.|
|ExpirationDate|date-time|false|true|Expiration date for the initial secret for the client.|
|Client|[ClientCredentialClient](#schemaclientcredentialclient)|false|true|Created client credential client.|

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

<h2 id="tocS_ClientCredentialClientCreate">ClientCredentialClientCreate</h2>

<a id="schemaclientcredentialclientcreate"></a>
<a id="schema_ClientCredentialClientCreate"></a>
<a id="tocSclientcredentialclientcreate"></a>
<a id="tocsclientcredentialclientcreate"></a>

```json
{
  "RoleIds": [
    "string"
  ],
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

Object used during Client creation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleIds|string[]|false|true|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|
|Id|string|false|true|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|false|true|Name of client.|
|Enabled|boolean|false|true|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|false|true|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|false|true|Tags for OSIsoft internal use only.|
|SecretDescription|string|false|true|Description for the initial secret for the client. Ensure that this is descriptive enough, as it will be the only way to distinguish between multiple secrets and their usage for a client.|
|SecretExpirationDate|date-time|false|true|Expiration date for the initial secret for the client. If set to null the secret will never expire. We advise against such practice.|

<h2 id="tocS_ClientCredentialClientMultiStatusResponse">ClientCredentialClientMultiStatusResponse</h2>

<a id="schemaclientcredentialclientmultistatusresponse"></a>
<a id="schema_ClientCredentialClientMultiStatusResponse"></a>
<a id="tocSclientcredentialclientmultistatusresponse"></a>
<a id="tocsclientcredentialclientmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
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
  ]
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Operation unique identifier that resulted in this error.|
|Error|string|false|true|Message describing the error.|
|Reason|string|false|true|Reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|List of child errors.|
|Data|[[ClientCredentialClient](#schemaclientcredentialclient)]|false|true|Data representing client credential client.|

<h2 id="tocS_MultiStatusResponseChildError">MultiStatusResponseChildError</h2>

<a id="schemamultistatusresponsechilderror"></a>
<a id="schema_MultiStatusResponseChildError"></a>
<a id="tocSmultistatusresponsechilderror"></a>
<a id="tocsmultistatusresponsechilderror"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "StatusCode": 0,
  "ModelId": "string",
  "property1": null,
  "property2": null
}

```

ChildError objects returned in a 207 response.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Operation unique identifier of action that caused the error.|
|Error|string|true|false|Error description.|
|Reason|string|true|false|Reason for the error.|
|Resolution|string|true|false|Resolution needed to resolve the Error.|
|StatusCode|int32|false|false|Http status code.|
|ModelId|string|false|true|Model Id.|

<h2 id="tocS_ClientCredentialClient2">ClientCredentialClient2</h2>

<a id="schemaclientcredentialclient2"></a>
<a id="schema_ClientCredentialClient2"></a>
<a id="tocSclientcredentialclient2"></a>
<a id="tocsclientcredentialclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ClientId|string|false|true|None|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Enabled|boolean|false|true|None|
|Tags|string[]|false|true|None|
|RoleIds|string[]|false|true|None|

<h2 id="tocS_ClientCredentialClientMultiStatusResponse2">ClientCredentialClientMultiStatusResponse2</h2>

<a id="schemaclientcredentialclientmultistatusresponse2"></a>
<a id="schema_ClientCredentialClientMultiStatusResponse2"></a>
<a id="tocSclientcredentialclientmultistatusresponse2"></a>
<a id="tocsclientcredentialclientmultistatusresponse2"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "ClientId": "string",
      "Id": "string",
      "Name": "string",
      "Enabled": true,
      "Tags": [
        "string"
      ],
      "RoleIds": [
        "string"
      ]
    }
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|[ChildError objects returned in a 207 response.]|
|Data|[[ClientCredentialClient2](#schemaclientcredentialclient2)]|false|true|None|

<h2 id="tocS_ClientCredentialClientResponse">ClientCredentialClientResponse</h2>

<a id="schemaclientcredentialclientresponse"></a>
<a id="schema_ClientCredentialClientResponse"></a>
<a id="tocSclientcredentialclientresponse"></a>
<a id="tocsclientcredentialclientresponse"></a>

```json
{
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "RoleIds": [
    "string"
  ],
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "ClientSecret": "string",
  "SecretId": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|SecretDescription|string|false|true|None|
|SecretExpirationDate|date-time|false|true|None|
|RoleIds|string[]|false|true|None|
|ClientId|string|false|true|None|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Enabled|boolean|false|true|None|
|Tags|string[]|false|true|None|
|ClientSecret|string|false|true|None|
|SecretId|string|false|true|None|

<h2 id="tocS_ClientCredentialClientCreate2">ClientCredentialClientCreate2</h2>

<a id="schemaclientcredentialclientcreate2"></a>
<a id="schema_ClientCredentialClientCreate2"></a>
<a id="tocSclientcredentialclientcreate2"></a>
<a id="tocsclientcredentialclientcreate2"></a>

```json
{
  "RoleIds": [
    "string"
  ],
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleIds|string[]|false|true|None|
|ClientId|string|false|true|None|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Enabled|boolean|false|true|None|
|Tags|string[]|false|true|None|
|SecretDescription|string|false|true|None|
|SecretExpirationDate|date-time|false|true|None|

