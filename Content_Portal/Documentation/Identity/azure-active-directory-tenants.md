---
title: Identity/azure-active-directory-tenants v20210317.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.6

---

[[_TOC_]]

# Azure Active Directory Tenants
An Azure Active Directory (AAD) Tenant is used to map an existing [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) Tenant from Azure to OSIsoft Cloud Services. We only allow one Azure Active Directory Tenant per OSIsoft Cloud Services Tenant.

## List Aad Tenants For Tenant

<a id="opIdAzureActiveDirectoryTenants_List Aad Tenants For Tenant"></a>

Get all Azure Active Directory Tenants from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
?query={query}&skip={skip}&count={count}
```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of Azure Active Directory tenants to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of Azure Active Directory tenants to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)[]|List of AzureActiveDirectoryTenants found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|or|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "ConsentState": 0,
    "Domain": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Get Aad Tenants Header For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenants Header For Tenant"></a>

Return total number of Azure Active Directory tenants in a OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants

```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for AzureActiveDirectoryTenants found.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Get Aad Tenant For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenant For Tenant"></a>

Get Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}

```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`
<br/>Id of Azure Active Directory Tenant.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectory specified.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Get Aad Tenant Header For Tenant

<a id="opIdAzureActiveDirectoryTenants_Get Aad Tenant Header For Tenant"></a>

Validate that Azure Active Directory Tenant exists in this OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}

```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`
<br/>Id of Azure Active Directory Tenant.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Azure Active Directory Tenant.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Add Aad Tenant To Tenant

<a id="opIdAzureActiveDirectoryTenants_Add Aad Tenant To Tenant"></a>

Add an Azure Active Directory Tenant to the OSIsoft Cloud Services Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}

```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`
<br/>Id or Domain Name of Azure Active Directory Tenant.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectoryTenant object created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Id of Azure Active Directory Tenant. is already in use on the specified Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Remove Aad Tenant From Tenant

<a id="opIdAzureActiveDirectoryTenants_Remove Aad Tenant From Tenant"></a>

Removal of Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant is not supported.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}

```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`
<br/>Id of Azure Active Directory Tenant to remove.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|NotSupportedException.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## Send Aad Tenant Consent Request

<a id="opIdAzureActiveDirectoryTenants_Send Aad Tenant Consent Request"></a>

Send consent for an Azure Active Directory Tenant. OSIsoft Cloud Services needs to be granted permission to interact with the Azure Active Directory tenant. Otherwise, users from this Azure Active Directory Tenant cannot accept invitations from OSIsoft Cloud Services and log in. You can read more about this [here](https://pisquare.osisoft.com/docs/DOC-3986-msa-consent-for-azure-active-directory).

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}/SendConsent

```

### Request Body

ConsentInformation object.<br/>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}
```

### Parameters

`string tenantId`
<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`
<br/>Id of Azure Active Directory Tenant.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
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
<li>Tenant Administrator</li>
</ul>

---
# Definitions

## AzureActiveDirectoryTenant

<a id="schemaazureactivedirectorytenant"></a>
<a id="schema_AzureActiveDirectoryTenant"></a>
<a id="tocSazureactivedirectorytenant"></a>
<a id="tocsazureactivedirectorytenant"></a>

The model for an AAD tenant in Identity Storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|AAD tenant unique identifier.|
|ConsentState|[ConsentState](#schemaconsentstate)|false|false|Consent state of AAD tenant. Can be: NotConsented (0), Consented (1).|
|Domain|string|false|true|AAD tenant domain name.|

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}

```

---

## ConsentState

<a id="schemaconsentstate"></a>
<a id="schema_ConsentState"></a>
<a id="tocSconsentstate"></a>
<a id="tocsconsentstate"></a>

AAD Tenant Consent State.

#### Enumerated Values

|Property|Value|
|---|---|
|NotConsented|0|
|Consented|1|

---

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned whenever there is an error.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Operation unique identifier of action that caused the error.|
|Error|string|true|false|Error description.|
|Reason|string|true|false|Reason for the error.|
|Resolution|string|true|false|Resolution to resolve the error.|

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

## ConsentInformation

<a id="schemaconsentinformation"></a>
<a id="schema_ConsentInformation"></a>
<a id="tocSconsentinformation"></a>
<a id="tocsconsentinformation"></a>

Information about the recipient of the Azure Active Directory consent email.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|email|false|true|Email address to send consent.|
|AzureActiveDirectoryConsentGivenName|string|false|true|Preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string|false|true|Preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string|false|true|AAD tenant domain name (for example, mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string|false|true|Semicolon delimited AAD consent types. Can be "SignIn" or "SignIn;ReadAllUsersGroups".|

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}

```

---

