---
title: Identity/claim-type-names v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-claim-type-names-claim-type-names">Claim Type Names</h1>
An identity provider claim type name is the attribute needed when creating an identity provider claim.

	

	

	

---
## List Identity Provider Claim Type Names

<a id="opIdClaimTypeNames_List Identity Provider Claim Type Names"></a>

Gets all identity provider claim type names for an identity provider on a tenant.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_list-identity-provider-claim-type-names-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of identity providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of identity providers to return.<br/><br/>

<h3 id="claimtypenames_list-identity-provider-claim-type-names-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaimTypeName](#schemaidentityproviderclaimtypename)[]|List of identity provider type names found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider not found.|
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
## Get Identity Provider Claim Type Names Header

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Names Header"></a>

Gets header for all identity provider claim type names for an identity provider on a tenant.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_get-identity-provider-claim-type-names-header-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-names-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for identity provider claim type names.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Claim Type Name

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Name"></a>

Gets an identity provider claim type name from an identity provider.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_get-identity-provider-claim-type-name-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimTypeNameId`<br/>Identity provider claim type name unique identifier.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-name-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity provider claim type name specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider, or identity provider claim type name not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Claim Type Name Header

<a id="opIdClaimTypeNames_Get Identity Provider Claim Type Name Header"></a>

Gets an identity provider claim type name header from an identity provider.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_get-identity-provider-claim-type-name-header-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string identityProviderClaimTypeNameId`<br/>Identity provider claim type name unique identifier.<br/><br/>

<h3 id="claimtypenames_get-identity-provider-claim-type-name-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for identity provider claim type name specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider, or identity provider claim type name not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

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

Claim type name associated with an identity provider.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Claim type name unique identifier.|
|TypeName|string|false|true|Claim Type Name.|
|IdentityProviderId|guid|false|false|Identity provider unique identifier associated with this claim type name.|

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

Object representing a claim from an identity provider to map to a role.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Identity provider claim unique identifier.|
|TypeName|string|false|true|Type name for this identity provider claim.|
|Value|string|false|true|Value for this identity provider claim.|
|RoleIds|string[]|false|true|List of role Ids that this claim on this identity provider will map to.|

