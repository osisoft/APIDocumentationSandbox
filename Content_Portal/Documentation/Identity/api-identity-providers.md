---
title: Identity/api-identity-providers v20210304.2
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-api-identity-providers-identity-providers">Identity Providers</h1>
APIs for getting a list of all supported identity providers.

The model for an Identity Provider in Identity Storage.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|guid|Identity provider unique identifier.|
|DisplayName|string|Identity provider display name to use.|
|Scheme|string|Name of the cookie handler that will temporarily store the outcome of the external authentication.|
|UserIdClaimType|string|Type of claim.|
|ClientId|string|Client Id of the identity provider.|
|IsConfigured|boolean|Whether the identity provider has been configured.|
|Capabilities|[IdentityProviderCapabilities](#schemaidentityprovidercapabilities)|Capabilities of the identity provider.|

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}
```

	

	

	

	

	

---
## List Identity Providers

<a id="opIdIdentityProviders_List Identity Providers"></a>

Returns a list of identity provider objects.

### Request
```text 
GET /api/v1/IdentityProviders
```

<h3 id="identityproviders_list-identity-providers-parameters">Parameters</h3>

`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of identity providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of identity providers to return.<br/><br/>

<h3 id="identityproviders_list-identity-providers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)[]|Identity providers found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Get Identity Providers Header

<a id="opIdIdentityProviders_Get Identity Providers Header"></a>

Get the total number of identity providers.

### Request
```text 
HEAD /api/v1/IdentityProviders
```

<h3 id="identityproviders_get-identity-providers-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for identity providers found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider

<a id="opIdIdentityProviders_Get Identity Provider"></a>

Returns an IdentityProvider object.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_get-identity-provider-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_get-identity-provider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Get Identity Provider Header

<a id="opIdIdentityProviders_Get Identity Provider Header"></a>

Validates that a identity provider exists

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_get-identity-provider-header-parameters">Parameters</h3>

`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_get-identity-provider-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider By Scheme

<a id="opIdIdentityProviders_Get Identity Provider By Scheme"></a>

Returns a list of identity provider objects that follow a scheme.

### Request
```text 
GET /api/v1/IdentityProviders/schemes/{scheme}
```

<h3 id="identityproviders_get-identity-provider-by-scheme-parameters">Parameters</h3>

`string scheme`<br/>Scheme name (for example, AAD or Google).<br/><br/>

<h3 id="identityproviders_get-identity-provider-by-scheme-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Get Identity Provider Scheme Header

<a id="opIdIdentityProviders_Get Identity Provider Scheme Header"></a>

Validates that a scheme exists

### Request
```text 
HEAD /api/v1/IdentityProviders/schemes/{scheme}
```

<h3 id="identityproviders_get-identity-provider-scheme-header-parameters">Parameters</h3>

`string scheme`<br/>Scheme name (for example, AAD or Google).<br/><br/>

<h3 id="identityproviders_get-identity-provider-scheme-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider found.|
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

# Definitions

<h2 id="tocS_IdentityProvider">IdentityProvider</h2>

<a id="schemaidentityprovider"></a>
<a id="schema_IdentityProvider"></a>
<a id="tocSidentityprovider"></a>
<a id="tocsidentityprovider"></a>

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}

```

The model for an Identity Provider in Identity Storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Identity provider unique identifier.|
|DisplayName|string|false|true|Identity provider display name to use.|
|Scheme|string|false|true|Name of the cookie handler that will temporarily store the outcome of the external authentication.|
|UserIdClaimType|string|false|true|Type of claim.|
|ClientId|string|false|true|Client Id of the identity provider.|
|IsConfigured|boolean|false|false|Whether the identity provider has been configured.|
|Capabilities|[IdentityProviderCapabilities](#schemaidentityprovidercapabilities)|false|true|Capabilities of the identity provider.|

<h2 id="tocS_IdentityProviderCapabilities">IdentityProviderCapabilities</h2>

<a id="schemaidentityprovidercapabilities"></a>
<a id="schema_IdentityProviderCapabilities"></a>
<a id="tocSidentityprovidercapabilities"></a>
<a id="tocsidentityprovidercapabilities"></a>

```json
{
  "User": {
    "SignIn": true,
    "Invitation": true,
    "Search": true
  },
  "Group": {
    "Authorize": true,
    "Search": true
  }
}

```

The model for the Capabilities of an Identity Provider in Identity Storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|User|[IdentityProviderUserCapabilites](#schemaidentityproviderusercapabilites)|false|true|Gets or sets user level capabilities|
|Group|[IdentityProviderGroupCapabilites](#schemaidentityprovidergroupcapabilites)|false|true|Gets or sets group level capabilities|

<h2 id="tocS_IdentityProviderUserCapabilites">IdentityProviderUserCapabilites</h2>

<a id="schemaidentityproviderusercapabilites"></a>
<a id="schema_IdentityProviderUserCapabilites"></a>
<a id="tocSidentityproviderusercapabilites"></a>
<a id="tocsidentityproviderusercapabilites"></a>

```json
{
  "SignIn": true,
  "Invitation": true,
  "Search": true
}

```

The model for the user level capabilities of an Identity Provider in Identity Storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|SignIn|boolean|false|false|Gets or sets a value indicating whether user sign-in is supported.|
|Invitation|boolean|false|false|Gets or sets a value indicating whether authorization via the invitation flow is supported.|
|Search|boolean|false|false|Gets or sets a value indicating whether user search is supported.|

<h2 id="tocS_IdentityProviderGroupCapabilites">IdentityProviderGroupCapabilites</h2>

<a id="schemaidentityprovidergroupcapabilites"></a>
<a id="schema_IdentityProviderGroupCapabilites"></a>
<a id="tocSidentityprovidergroupcapabilites"></a>
<a id="tocsidentityprovidergroupcapabilites"></a>

```json
{
  "Authorize": true,
  "Search": true
}

```

The model for the group level capabilities of an Identity Provider in Identity Storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Authorize|boolean|false|false|Gets or sets a value indicating whether authorization via groups is supported.|
|Search|boolean|false|false|Gets or sets a value indicating whether group search is supported.|

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

