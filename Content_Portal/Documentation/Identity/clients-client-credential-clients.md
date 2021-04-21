---
title: Identity/clients-client-credential-clients v20210421.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Client Credential Clients
APIs for getting, adding, or removing Client Credential clients from Communities.

## List Client Credential clients for a Community

<a id="opIdClientCredentialClients_List Client Credential clients for a Community"></a>

Get Clients associated with a specific Tenant and Community.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
?query={query}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant. Tenant must belong to the Community.<br/><br/>`string communityId`
<br/>The identifier of the Community.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of records to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of records to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)[]|Set of Clients ( `ClientCredentialClient`) associated with the Tenant ( `tenantId`) and Community ( `communityId`).|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
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
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Member</li>
</ul>

---

## Get Count of Clients for a Community

<a id="opIdClientCredentialClients_Get Count of Clients for a Community"></a>

Get Client Credential Client Count for a Community.

### Request
```text 
HEAD /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
```

#### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of the Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Member</li>
</ul>

---

## Add Client Credential Client to a Community

<a id="opIdClientCredentialClients_Add Client Credential Client to a Community"></a>

Add a Client Credential Client to a Community, providing a List of Community Role Ids to be assigned to the Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

#### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string clientId`
<br/>Id of the Client Credential Client to add to the specified Community.<br/><br/>

### Request Body

List of Community Role Ids to assign to the Client.<br/>

```json
[
  "string"
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Ok.|
|201|[ClientCredentialClient](#schemaclientcredentialclient)|Created.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

---

## Remove Client Credential Client from a Community

<a id="opIdClientCredentialClients_Remove Client Credential Client from a Community"></a>

Remove a Client Credential Client from a Community.

### Request
```text 
DELETE /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

#### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string clientId`
<br/>Id of the Client Credential Client to remove from the specified Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Removed.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

---
# Definitions

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned whenever there is an error. TODO: Remove this internal model and re-adopt public model when moving to System.Text.Json in WI 202168.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|

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

---

## ClientCredentialClient

<a id="schemaclientcredentialclient"></a>
<a id="schema_ClientCredentialClient"></a>
<a id="tocSclientcredentialclient"></a>
<a id="tocsclientcredentialclient"></a>

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

