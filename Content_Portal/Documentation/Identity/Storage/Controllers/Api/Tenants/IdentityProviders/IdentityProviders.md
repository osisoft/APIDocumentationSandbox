

<h1 id="identity-storage-controllers-api-tenants-identityproviders-identityproviders-identityproviders">IdentityProviders</h1>

## GetTenantIdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProviders"></a>

Get all Identity Providers from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_gettenantidentityproviders-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of Identity Providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of Identity Providers to return.<br/><br/>

<h3 id="identityproviders_gettenantidentityproviders-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProvider](#schemaidentityprovider)s|Identity Providers found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## AddTenantIdentityProvider

<a id="opIdIdentityProviders_AddTenantIdentityProvider"></a>

Add an existing Identity Provider to a Tenant. This Identity Provider will be available in the Home Realm Discovery Page for users to sign-in or sign-up.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders
```

### Request Body

IdentityProviderAdd object.<br/>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string",
  "IdentityProviderId": "string",
  "AzureActiveDirectorySendConsent": true
}
```

<h3 id="identityproviders_addtenantidentityprovider-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="identityproviders_addtenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProvider](#schemaidentityprovider)|Identity Provider created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider already exists in Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

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

## GetTenantIdentityProvidersHeader

<a id="opIdIdentityProviders_GetTenantIdentityProvidersHeader"></a>

Return total number of Identity Providers in a Tenant. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_gettenantidentityprovidersheader-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="identityproviders_gettenantidentityprovidersheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider headers for Tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## GetTenantIdentityProvider

<a id="opIdIdentityProviders_GetTenantIdentityProvider"></a>

Get an Identity Provider from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_gettenantidentityprovider-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_gettenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity Provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## RemoveTenantIdentityProvider

<a id="opIdIdentityProviders_RemoveTenantIdentityProvider"></a>

Remove an Identity Provider from a Tenant. Users provisioned with this Identity Provider will remain in the Tenant, but will not be able to authenticate. An administrator cannot remove the Identity Provider they are signed in with.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_removetenantidentityprovider-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_removetenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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

## GetTenantIdentityProviderHeader

<a id="opIdIdentityProviders_GetTenantIdentityProviderHeader"></a>

Validate that a Identity Provider exists in the Tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_gettenantidentityproviderheader-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_gettenantidentityproviderheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|IdentityProvider or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## GetTenantIdentityProviderConsent

<a id="opIdIdentityProviders_GetTenantIdentityProviderConsent"></a>

Get an Identity Provider Consent from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_gettenantidentityproviderconsent-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_gettenantidentityproviderconsent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity Provider Consent.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
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
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## UpdateTenantIdentityProviderConsent

<a id="opIdIdentityProviders_UpdateTenantIdentityProviderConsent"></a>

Update an Identity Provider consent related to Deeper Integration.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

### Request Body

Identity Provider Consent.<br/>

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}
```

<h3 id="identityproviders_updatetenantidentityproviderconsent-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_updatetenantidentityproviderconsent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity Provider Consent.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
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

## GetTenantIdentityProviderConsentHeader

<a id="opIdIdentityProviders_GetTenantIdentityProviderConsentHeader"></a>

Get header for an Identity Provider to check if any additional consent data exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_gettenantidentityproviderconsentheader-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Id of Identity Provider.<br/><br/>

<h3 id="identityproviders_gettenantidentityproviderconsentheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Ok if the Identity Provider Consent exists.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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
<li>Account Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## GetIdentityProviderUsers

<a id="opIdIdentityProviders_GetIdentityProviderUsers"></a>

Get the users based on the query parameters. Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/users
```

<h3 id="identityproviders_getidentityproviderusers-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>`string query`<br/>Start of user name or Email to search for.<br/><br/>
`[optional] integer count`<br/>Sets the page size of results.<br/><br/>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.<br/><br/>

<h3 id="identityproviders_getidentityproviderusers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderUser](#schemaidentityproviderresultsofidentityprovideruser)|List of users found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
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

## GetIdentityProviderGroups

<a id="opIdIdentityProviders_GetIdentityProviderGroups"></a>

Get the groups based on the query parameters. Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups
```

<h3 id="identityproviders_getidentityprovidergroups-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>`string query`<br/>Start of user name or Email to search for.<br/><br/>
`[optional] integer count`<br/>Sets the page size of results.<br/><br/>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.<br/><br/>

<h3 id="identityproviders_getidentityprovidergroups-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
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

## GetIdentityProviderGroupsForUser

<a id="opIdIdentityProviders_GetIdentityProviderGroupsForUser"></a>

Get the groups a user is a member of. Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Users/{userId}/Groups
```

<h3 id="identityproviders_getidentityprovidergroupsforuser-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>`string userId`<br/>Id of the user.<br/><br/>
`[optional] integer skip`<br/>Indexes into a result set.<br/><br/>`[optional] integer count`<br/>Sets the page size of results.<br/><br/>`[optional] integer timeout`<br/>The maximum time to allow for searching groups before returning the groups.<br/><br/>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.<br/><br/>

<h3 id="identityproviders_getidentityprovidergroupsforuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups user is a member of.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
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

## GetIdentityProviderGroupsByIds

<a id="opIdIdentityProviders_GetIdentityProviderGroupsByIds"></a>

Get the groups based on the Ids. Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Groups
```

### Request Body

Group Id list.<br/>

```json
[
  "string"
]
```

<h3 id="identityproviders_getidentityprovidergroupsbyids-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>

<h3 id="identityproviders_getidentityprovidergroupsbyids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
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

## GetIdentityProviderMembersInAGroup

<a id="opIdIdentityProviders_GetIdentityProviderMembersInAGroup"></a>

Get the members in a group. Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups/{groupId}/members
```

<h3 id="identityproviders_getidentityprovidermembersinagroup-parameters">Parameters</h3>

`string tenantId`<br/>Tenant Id.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>`string groupId`<br/>External Id of the group.<br/><br/>
`[optional] integer count`<br/>Sets the page size of results.<br/><br/>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.<br/><br/>

<h3 id="identityproviders_getidentityprovidermembersinagroup-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderMembers](#schemaidentityprovidermembers)|List of members.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Users": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "Groups": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets id of an identity provider.|
|DisplayName|string|false|true|Gets or sets identity provider display name to use.|
|Scheme|string|false|true|Gets or sets the name of the cookie handler that will temporarily store the outcome of the external authentication.|
|UserIdClaimType|string|false|true|Gets or sets type of claim.|
|ClientId|string|false|true|Gets or sets the ClientId of the identity provider.|
|IsConfigured|boolean|false|false|Gets or sets a value indicating whether the identity provider has been configured.|
|Capabilities|[IdentityProviderCapabilities](#schemaidentityprovidercapabilities)|false|true|Gets or sets the Capabilities of the identity provider.|

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

|Name|Type|Required|Nullable|Description|
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

|Name|Type|Required|Nullable|Description|
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

|Name|Type|Required|Nullable|Description|
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

<h2 id="tocS_IdentityProviderConsent">IdentityProviderConsent</h2>

<a id="schemaidentityproviderconsent"></a>
<a id="schema_IdentityProviderConsent"></a>
<a id="tocSidentityproviderconsent"></a>
<a id="tocsidentityproviderconsent"></a>

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}

```

The model for an Identity Provider Consent in Identity Storage.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Scheme|string|false|true|Gets or sets the scheme of the Identity Provider.|

<h2 id="tocS_IdentityProviderAdd">IdentityProviderAdd</h2>

<a id="schemaidentityprovideradd"></a>
<a id="schema_IdentityProviderAdd"></a>
<a id="tocSidentityprovideradd"></a>
<a id="tocsidentityprovideradd"></a>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string",
  "IdentityProviderId": "string",
  "AzureActiveDirectorySendConsent": true
}

```

Object for adding an Identity Provider.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|email|false|true|Gets or sets address to email consent.|
|AzureActiveDirectoryConsentGivenName|string|false|true|Gets or sets preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string|false|true|Gets or sets preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string|false|true|Gets or sets Azure Active Directory Domain Name (e.g. mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string|false|true|Gets or sets Azure Active Directory Consent Types. Valid Consent Type combinations include "SignIn" and "SignIn;ReadAllUsersGroups".|
|IdentityProviderId|guid|false|false|Gets or sets Identity Provider Id to Add.|
|AzureActiveDirectorySendConsent|boolean|false|false|Gets or sets a value indicating whether send consent email for Azure Active Directory.|

<h2 id="tocS_IdentityProviderResultsOfIdentityProviderUser">IdentityProviderResultsOfIdentityProviderUser</h2>

<a id="schemaidentityproviderresultsofidentityprovideruser"></a>
<a id="schema_IdentityProviderResultsOfIdentityProviderUser"></a>
<a id="tocSidentityproviderresultsofidentityprovideruser"></a>
<a id="tocsidentityproviderresultsofidentityprovideruser"></a>

```json
{
  "Results": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Result object for Identity Provider access users/groups.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|[[IdentityProviderUser](#schemaidentityprovideruser)]|false|false|List of users/groups.|
|SkipToken|string|false|true|Skip token for paging.|

<h2 id="tocS_IdentityProviderUser">IdentityProviderUser</h2>

<a id="schemaidentityprovideruser"></a>
<a id="schema_IdentityProviderUser"></a>
<a id="tocSidentityprovideruser"></a>
<a id="tocsidentityprovideruser"></a>

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "user@example.com"
}

```

Base class for Identity provider access user.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|false|Gets or sets Id of user.|
|GivenName|string|false|true|Gets or sets given name of user.|
|Surname|string|false|true|Gets or sets surname of user.|
|Name|string|false|true|Gets or sets name of user.|
|Email|email|false|true|Gets or sets email of user.|

<h2 id="tocS_IdentityProviderResultsOfIdentityProviderGroup">IdentityProviderResultsOfIdentityProviderGroup</h2>

<a id="schemaidentityproviderresultsofidentityprovidergroup"></a>
<a id="schema_IdentityProviderResultsOfIdentityProviderGroup"></a>
<a id="tocSidentityproviderresultsofidentityprovidergroup"></a>
<a id="tocsidentityproviderresultsofidentityprovidergroup"></a>

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Result object for Identity Provider access users/groups.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|[[IdentityProviderGroup](#schemaidentityprovidergroup)]|false|false|List of users/groups.|
|SkipToken|string|false|true|Skip token for paging.|

<h2 id="tocS_IdentityProviderGroup">IdentityProviderGroup</h2>

<a id="schemaidentityprovidergroup"></a>
<a id="schema_IdentityProviderGroup"></a>
<a id="tocSidentityprovidergroup"></a>
<a id="tocsidentityprovidergroup"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Email": "user@example.com"
}

```

Base class for Identity Provider access group.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|false|Gets or sets the Object Id of IdentityProviderGroup.|
|Name|string|false|true|Gets or sets group name of IdentityProviderGroup.|
|Email|email|false|true|Gets or sets the email address of the IdentityProviderGroup.|

<h2 id="tocS_IdentityProviderMembers">IdentityProviderMembers</h2>

<a id="schemaidentityprovidermembers"></a>
<a id="schema_IdentityProviderMembers"></a>
<a id="tocSidentityprovidermembers"></a>
<a id="tocsidentityprovidermembers"></a>

```json
{
  "Users": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "Groups": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Class to hold members in a group.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Users|[[IdentityProviderUser](#schemaidentityprovideruser)]|false|false|List of users.|
|Groups|[[IdentityProviderGroup](#schemaidentityprovidergroup)]|false|false|List of groups.|
|SkipToken|string|false|true|Skip token for paging.|

