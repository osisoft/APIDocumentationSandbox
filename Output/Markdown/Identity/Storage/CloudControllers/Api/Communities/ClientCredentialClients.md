

<h1 id="identity-storage-cloudcontrollers-api-communities-clientcredentialclients-clientcredentialclients">ClientCredentialClients</h1>

## Get Community Client Credential Clients

<a id="opIdClientCredentialClients_Get Community Client Credential Clients"></a>

Get Client Credential clients for a Community.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_get-community-client-credential-clients-parameters">Parameters</h3>

`string tenantId`<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`<br/>Id of Community.<br/><br/>

<h3 id="clientcredentialclients_get-community-client-credential-clients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientCredentialClient](#schemaclientcredentialclient)s|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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
<li>Community Member</li>
</ul>

## Get Community Client Credential Clients Count

<a id="opIdClientCredentialClients_Get Community Client Credential Clients Count"></a>

Get Client Credential Client Count for a Community.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_get-community-client-credential-clients-count-parameters">Parameters</h3>

`string tenantId`<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`<br/>Id of the Community.<br/><br/>

<h3 id="clientcredentialclients_get-community-client-credential-clients-count-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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
<li>Community Member</li>
</ul>

## Add Client Credential Client To Community

<a id="opIdClientCredentialClients_Add Client Credential Client To Community"></a>

Add a Client Credential Client to a Community.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_add-client-credential-client-to-community-parameters">Parameters</h3>

`string tenantId`<br/>Id of the Tenant that belongs to this Community<br/><br/>`string communityId`<br/>Id of Community.<br/><br/>`string clientId`<br/>Id of the Client Credential Client to add to the specified Community.<br/><br/>

<h3 id="clientcredentialclients_add-client-credential-client-to-community-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClient](#schemaclientcredentialclient)|Created.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

## Remove Client Credential Client From Community

<a id="opIdClientCredentialClients_Remove Client Credential Client From Community"></a>

Remove a Client Credential Client from a Community.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_remove-client-credential-client-from-community-parameters">Parameters</h3>

`string tenantId`<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`<br/>Id of Community.<br/><br/>`string clientId`<br/>Id of the Client Credential Client to remove from the specified Community.<br/><br/>

<h3 id="clientcredentialclients_remove-client-credential-client-from-community-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Removed.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

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
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

# Schemas

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

