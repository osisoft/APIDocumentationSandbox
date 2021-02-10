

<h1 id="identity-storage-controllers-api-tenants-identityproviders-claims-claims">Claims</h1>

## Get Identity Provider Claims

<a id="opIdClaims_Get Identity Provider Claims"></a>

Get all Identity Provider Claims for an Identity Provider on a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_get-identity-provider-claims-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of Identity Providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of Identity Providers to return.<br/><br/>

<h3 id="claims_get-identity-provider-claims-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProviderClaim](#schemaidentityproviderclaim)s|List of Identity Provider Claims found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Identity Provider not found.|
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
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Get Identity Provider Claims Header

<a id="opIdClaims_Get Identity Provider Claims Header"></a>

Get Header for all Identity Provider Claims for an Identity Provider on a Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_get-identity-provider-claims-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="claims_get-identity-provider-claims-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider Claim Header information.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Identity Provider not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Post Identity Provider Claim

<a id="opIdClaims_Post Identity Provider Claim"></a>

Create a new Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

### Request Body

Identity Provider Claim to create.<br/>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_post-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="claims_post-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Provider Claim created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider Claim configuration already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
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

## Get Identity Provider Claim

<a id="opIdClaims_Get Identity Provider Claim"></a>

Get an Identity Provider Claim from an Identity Provider on a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_get-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimId`<br/>Id of Identity Provider Claim.<br/><br/>

<h3 id="claims_get-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Provider Claim specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Identity Provider Claim not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
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

## Get Identity Provider Claim Header

<a id="opIdClaims_Get Identity Provider Claim Header"></a>

Get an Identity Provider Claim Header from an Identity Provider on a Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_get-identity-provider-claim-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimId`<br/>Id of Identity Provider Claim.<br/><br/>

<h3 id="claims_get-identity-provider-claim-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider Claim specified header.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant, Identity Provider, or Identity Provider Claim not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Put Identity Provider Claim

<a id="opIdClaims_Put Identity Provider Claim"></a>

Create a new Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

### Request Body

Updated Identity Provider Claim values.<br/>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_put-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimId`<br/>Id of Identity Provider Claim.<br/><br/>

<h3 id="claims_put-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Updated Identity Provider Claim.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, Identity Provider Claim, or Roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider Claim configuration already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
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

## Delete Identity Provider Claim

<a id="opIdClaims_Delete Identity Provider Claim"></a>

Delete an Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_delete-identity-provider-claim-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimId`<br/>Id of Identity Provider Claim.<br/><br/>

<h3 id="claims_delete-identity-provider-claim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Identity Provider Claim not found.|
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
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

# Schemas

<h2 id="tocS_IdentityProviderClaim">IdentityProviderClaim</h2>

<a id="schemaidentityproviderclaim"></a>
<a id="schema_IdentityProviderClaim"></a>
<a id="tocSidentityproviderclaim"></a>
<a id="tocsidentityproviderclaim"></a>

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object representing a claim from an Identity Provider to map to a Role.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets the IdentityProvider Claim Id.|
|TypeName|string|false|true|Gets or sets the Type Name for this IdentityProvider Claim.|
|Value|string|false|true|Gets or sets the value for this IdentityProvider Claim.|
|RoleIds|List of strings|false|true|Gets or sets a list of RoleIds that this claim on this IdentityProvider will map to.|

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

<h2 id="tocS_IdentityProviderClaimCreate">IdentityProviderClaimCreate</h2>

<a id="schemaidentityproviderclaimcreate"></a>
<a id="schema_IdentityProviderClaimCreate"></a>
<a id="tocSidentityproviderclaimcreate"></a>
<a id="tocsidentityproviderclaimcreate"></a>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}

```

IdentityProvider Claim to Create.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|string|false|true|Gets or sets the value for this IdentityProvider Claim.|
|IdentityProviderClaimTypeNameId|guid|false|false|Gets or sets the Identity Provider Claim Type Name Id for this IdentityProvider Claim.|
|RoleIds|List of strings|false|true|Gets or sets the list of Role Ids associated with this IdentityProviderClaim.|

<h2 id="tocS_IdentityProviderClaimUpdate">IdentityProviderClaimUpdate</h2>

<a id="schemaidentityproviderclaimupdate"></a>
<a id="schema_IdentityProviderClaimUpdate"></a>
<a id="tocSidentityproviderclaimupdate"></a>
<a id="tocsidentityproviderclaimupdate"></a>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Update information for an IdentityProvider Claim.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|string|false|true|Gets or sets the value for this IdentityProvider Claim.|
|RoleIds|List of strings|false|true|Gets or sets the list of Role Ids associated with this IdentityProviderClaim.|

