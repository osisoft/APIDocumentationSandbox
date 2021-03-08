---
title: Identity/device-code-clients v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-device-code-clients-device-code-clients">Device Code Clients</h1>
Device Code clients are used in browserless or input constrained devices. These clients are issued an ID. Device Code clients are not issued secrets.

Object used for device code clients.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|string|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|Name of client.|
|Enabled|boolean|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|Tags for OSIsoft internal use only.|
|DeviceCodeLifetime|int32|Lifetime of device codes in seconds.|
|ClientUri|string|URI to a page with information about client (used on consent screen).|
|LogoUri|string|URI to client logo (used on consent screen).|

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

	

	

	

---
## List Device Code Clients

<a id="opIdDeviceCodeClients_List Device Code Clients"></a>

Get all Device Code clients from a Tenant. Optionally, get a list of requested clients. Total number of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

<h3 id="devicecodeclients_list-device-code-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only return Clients that have these tags.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of clients to skip. From query.<br/><br/>`[optional] integer count`<br/>Maximum number of clients to return.<br/><br/>

<h3 id="devicecodeclients_list-device-code-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeviceCodeClient](#schemadevicecodeclient)[]|Device Code Clients found.|
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
## Get Device Code Clients Header

<a id="opIdDeviceCodeClients_Get Device Code Clients Header"></a>

Return total number of Device Code clients in a Tenant. Optionally, check based on a list of requested clients. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

<h3 id="devicecodeclients_get-device-code-clients-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.<br/><br/>`[optional] array tag`<br/>Only count Clients that have these tags.<br/><br/>

<h3 id="devicecodeclients_get-device-code-clients-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Device Code Client headers.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
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
## Create Device Code Client

<a id="opIdDeviceCodeClients_Create Device Code Client"></a>

Create an Device Code flow Client. No Secret will be generated for this Client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

### Request Body

New DeviceCodeClient object.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

<h3 id="devicecodeclients_create-device-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="devicecodeclients_create-device-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client created.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Device Code Client

<a id="opIdDeviceCodeClients_Get Device Code Client"></a>

Get an Device Code Client from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_get-device-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="devicecodeclients_get-device-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client specified.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
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
## Get Device Code Client Header

<a id="opIdDeviceCodeClients_Get Device Code Client Header"></a>

Validate that an Device Code Client exists in Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_get-device-code-client-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="devicecodeclients_get-device-code-client-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Header for specified Device Code Client.|
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
## Update Device Code Client

<a id="opIdDeviceCodeClients_Update Device Code Client"></a>

Update an Device Code Client. It can take up to one hour for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

### Request Body

Updated Device Code Client values. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

<h3 id="devicecodeclients_update-device-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="devicecodeclients_update-device-code-client-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client updated.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete Device Code Client

<a id="opIdDeviceCodeClients_Delete Device Code Client"></a>

Delete a Device Code Client. It can take up to one hour for deletion to manifest in the authentication process. Access tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_delete-device-code-client-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string clientId`<br/>Id of Client.<br/><br/>

<h3 id="devicecodeclients_delete-device-code-client-responses">Responses</h3>

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

<h2 id="tocS_DeviceCodeClient">DeviceCodeClient</h2>

<a id="schemadevicecodeclient"></a>
<a id="schema_DeviceCodeClient"></a>
<a id="tocSdevicecodeclient"></a>
<a id="tocsdevicecodeclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}

```

Object used for device code clients.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Client unique identifier for this client. This unique identifier should be a GUID.|
|Name|string|false|true|Name of client.|
|Enabled|boolean|false|true|Whether client is enabled. Client can be used for authentication if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|int32|false|true|Lifetime of access token issued for this client after authentication. Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|string[]|false|true|Tags for OSIsoft internal use only.|
|DeviceCodeLifetime|int32|false|true|Lifetime of device codes in seconds.|
|ClientUri|string|false|true|URI to a page with information about client (used on consent screen).|
|LogoUri|string|false|true|URI to client logo (used on consent screen).|

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

