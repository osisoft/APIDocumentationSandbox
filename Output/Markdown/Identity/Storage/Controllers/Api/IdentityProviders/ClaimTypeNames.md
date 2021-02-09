

<h1 id="identity-storage-controllers-api-identityproviders-claimtypenames-claimtypenames">ClaimTypeNames</h1>

## Get Identity Provider Claim Type Names

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Names"></a>

Get all Identity Provider Claim Type Names for an Identity Provider.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_get-identity-provider-claim-type-names-parameters">Parameters</h3>

`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of Identity Providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of Identity Providers to return.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-names-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProviderClaimTypeName](#schemaidentityproviderclaimtypename)s|Identity Provider Type Names found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider not found.|
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

## Get Identity Provider Claim Type Names Header

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Names Header"></a>

Get Header for all Identity Provider Claims Type Names for an Identity Provider.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_get-identity-provider-claim-type-names-header-parameters">Parameters</h3>

`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-names-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider Claim Type Names.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity Provider not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Get Identity Provider Claim Type Name

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Name"></a>

Get an Identity Provider Claim Type Name from an Identity Provider.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_get-identity-provider-claim-type-name-parameters">Parameters</h3>

`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimTypeNameId`<br/>Id of Identity Provider Claim Type Name.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-name-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Proivder Claim Type Name specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider, or Identity Provider Claim Type Name not found.|
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

## Get Identity Provider Claim Type Name Header

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Name Header"></a>

Get an Identity Provider Claim Type Name Header from an Identity Provider.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_get-identity-provider-claim-type-name-header-parameters">Parameters</h3>

`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>`string identityProviderClaimTypeNameId`<br/>Id of Identity Provider Claim Type Name.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-name-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider Claim Type Name specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity Provider, or Identity Provider Claim Type Name not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

# Schemas

<h2 id="tocS_IdentityProviderClaimTypeName">IdentityProviderClaimTypeName</h2>

<a id="schemaidentityproviderclaimtypename"></a>
<a id="schema_IdentityProviderClaimTypeName"></a>
<a id="tocSidentityproviderclaimtypename"></a>
<a id="tocsidentityproviderclaimtypename"></a>

```json
{
  "Id": "string",
  "TypeName": "string",
  "IdentityProviderId": "string"
}

```

Claim Type Name associated with an Identity Provider.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets the ID for this Claim Type Name.|
|TypeName|string|false|true|Gets or sets the Claim Type Name.|
|IdentityProviderId|guid|false|false|Gets or sets the Identity Provider Id associated with this Claim Type Name.|

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

