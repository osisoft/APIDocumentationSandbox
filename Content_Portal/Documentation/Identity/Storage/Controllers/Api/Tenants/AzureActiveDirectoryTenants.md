

<h1 id="identity-storage-controllers-api-tenants-azureactivedirectorytenants-azureactivedirectorytenants">AzureActiveDirectoryTenants</h1>

## AddAadTenantToTenant

<a id="opIdAzureActiveDirectoryTenants_AddAadTenantToTenant"></a>

Add an Azure Active Directory Tenant to the OSIsoft Cloud Services Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_addaadtenanttotenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id or Domain Name of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_addaadtenanttotenant-responses">Responses</h3>

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

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

> 400 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 403 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 404 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 408 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 409 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 500 Response

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
</ul>

## GetAadTenantForTenant

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantForTenant"></a>

Get Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_getaadtenantfortenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_getaadtenantfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectory specified.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

> 400 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 403 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 404 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 500 Response

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
</ul>

## RemoveAadTenantFromTenant

<a id="opIdAzureActiveDirectoryTenants_RemoveAadTenantFromTenant"></a>

Removal of Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant is not supported.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_removeaadtenantfromtenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant to remove.<br/><br/>

<h3 id="azureactivedirectorytenants_removeaadtenantfromtenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|NotSupportedException.|

### Example response body

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## GetAadTenantHeaderForTenant

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantHeaderForTenant"></a>

Validate that Azure Active Directory Tenant exists in this OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_getaadtenantheaderfortenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_getaadtenantheaderfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Azure Active Directory Tenant.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## GetAadTenantsForTenant

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantsForTenant"></a>

Get all Azure Active Directory Tenants from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_getaadtenantsfortenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of Azure Active Directory tenants to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of Azure Active Directory tenants to return.<br/><br/>

<h3 id="azureactivedirectorytenants_getaadtenantsfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)s|List of AzureActiveDirectoryTenants found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|or|
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

> 403 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 500 Response

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
</ul>

## GetAadTenantsHeaderForTenant

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantsHeaderForTenant"></a>

Return total number of Azure Active Directory tenants in a OSIsoft Cloud Services Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_getaadtenantsheaderfortenant-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_getaadtenantsheaderfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for AzureActiveDirectoryTenants found.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## SendAadTenantConsentRequest

<a id="opIdAzureActiveDirectoryTenants_SendAadTenantConsentRequest"></a>

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

<h3 id="azureactivedirectorytenants_sendaadtenantconsentrequest-parameters">Parameters</h3>

`string tenantId`<br/>Id of OSIsoft Cloud Services Tenant.<br/><br/>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.<br/><br/>

<h3 id="azureactivedirectorytenants_sendaadtenantconsentrequest-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
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

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 403 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 404 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 500 Response

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
</ul>

# Schemas

<h2 id="tocS_AzureActiveDirectoryTenant">AzureActiveDirectoryTenant</h2>

<a id="schemaazureactivedirectorytenant"></a>
<a id="schema_AzureActiveDirectoryTenant"></a>
<a id="tocSazureactivedirectorytenant"></a>
<a id="tocsazureactivedirectorytenant"></a>

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}

```

The model for an Azure Active Directory Tenant in Identity Storage.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets id of an Azure Active Directory Tenant.|
|ConsentState|[ConsentState](#schemaconsentstate)|false|false|Gets or sets Consent State of Azure Active Directory Tenant. Can be: NotConsented (0), Consented (1).|
|Domain|string|false|true|Gets or sets Domain of Azure Active Directory Tenant.|

<h2 id="tocS_ConsentState">ConsentState</h2>

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

<h2 id="tocS_ConsentInformation">ConsentInformation</h2>

<a id="schemaconsentinformation"></a>
<a id="schema_ConsentInformation"></a>
<a id="tocSconsentinformation"></a>
<a id="tocsconsentinformation"></a>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}

```

Information about the recipient of the Azure Active Directory consent email.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|email|false|true|Gets or sets address to email consent.|
|AzureActiveDirectoryConsentGivenName|string|false|true|Gets or sets preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string|false|true|Gets or sets preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string|false|true|Gets or sets Azure Active Directory Domain Name (e.g. mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string|false|true|Gets or sets Azure Active Directory Consent Types. Valid Consent Type combinations include "SignIn" and "SignIn;ReadAllUsersGroups".|

