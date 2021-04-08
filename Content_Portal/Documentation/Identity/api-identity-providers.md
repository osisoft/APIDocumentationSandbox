---
title: Identity/api-identity-providers v20210407.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Identity Providers
APIs for getting a list of all supported identity providers.

## List Identity Providers

<a id="opIdIdentityProviders_List Identity Providers"></a>

Returns a list of identity provider objects.

### Request
```text 
GET /api/v1/IdentityProviders
?query={query}&skip={skip}&count={count}
```

#### Parameters

`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of identity providers to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of identity providers to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)[]|Identity providers found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "DisplayName": "string",
    "Scheme": "string",
    "UserIdClaimType": "string",
    "ClientId": "string",
    "IsConfigured": true,
    "Capabilities": {
      "User": {},
      "Group": {}
    }
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## Get Header for Identity Providers

<a id="opIdIdentityProviders_Get Header for Identity Providers"></a>

Get the total number of identity providers.

### Request
```text 
HEAD /api/v1/IdentityProviders
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for identity providers found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
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

#### Parameters

`string identityProviderId`
<br/>Identity provider unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## Get Identity Provider based on Id

<a id="opIdIdentityProviders_Get Identity Provider based on Id"></a>

Validates that a identity provider exists

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}
```

#### Parameters

`string identityProviderId`
<br/>Identity provider unique identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Get Identity Provider by Scheme

<a id="opIdIdentityProviders_Get Identity Provider by Scheme"></a>

Returns a list of identity provider objects that follow a scheme.

### Request
```text 
GET /api/v1/IdentityProviders/schemes/{scheme}
```

#### Parameters

`string scheme`
<br/>Scheme name (for example, AAD or Google).<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## Get Identity Provider Based on Scheme

<a id="opIdIdentityProviders_Get Identity Provider Based on Scheme"></a>

Validates that a scheme exists

### Request
```text 
HEAD /api/v1/IdentityProviders/schemes/{scheme}
```

#### Parameters

`string scheme`
<br/>Scheme name (for example, AAD or Google).<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## IdentityProvider

<a id="schemaidentityprovider"></a>
<a id="schema_IdentityProvider"></a>
<a id="tocSidentityprovider"></a>
<a id="tocsidentityprovider"></a>

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

## IdentityProviderCapabilities

<a id="schemaidentityprovidercapabilities"></a>
<a id="schema_IdentityProviderCapabilities"></a>
<a id="tocSidentityprovidercapabilities"></a>
<a id="tocsidentityprovidercapabilities"></a>

The model for the capabilities of an identity provider.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|User|[IdentityProviderUserCapabilites](#schemaidentityproviderusercapabilites)|false|true|User level capabilities.|
|Group|[IdentityProviderGroupCapabilites](#schemaidentityprovidergroupcapabilites)|false|true|Group level capabilities.|

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

---

## IdentityProviderUserCapabilites

<a id="schemaidentityproviderusercapabilites"></a>
<a id="schema_IdentityProviderUserCapabilites"></a>
<a id="tocSidentityproviderusercapabilites"></a>
<a id="tocsidentityproviderusercapabilites"></a>

The model for the user level capabilities of an identity provider.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|SignIn|boolean|false|false|Value indicating whether user log in is supported.|
|Invitation|boolean|false|false|Value indicating whether authorization via the invitation flow is supported.|
|Search|boolean|false|false|Value indicating whether user search is supported.|

```json
{
  "SignIn": true,
  "Invitation": true,
  "Search": true
}

```

---

## IdentityProviderGroupCapabilites

<a id="schemaidentityprovidergroupcapabilites"></a>
<a id="schema_IdentityProviderGroupCapabilites"></a>
<a id="tocSidentityprovidergroupcapabilites"></a>
<a id="tocsidentityprovidergroupcapabilites"></a>

The model for the group level capabilities of an identity provider.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Authorize|boolean|false|false|Value indicating whether authorization via groups is supported.|
|Search|boolean|false|false|Value indicating whether group search is supported.|

```json
{
  "Authorize": true,
  "Search": true
}

```

---

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|

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

