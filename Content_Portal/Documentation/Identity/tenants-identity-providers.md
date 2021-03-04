---
title: Identity/tenants-identity-providers v20210304.3
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-tenants-identity-providers-identity-providers">Identity Providers</h1>
An identity provider provides authentication services and maintains credentials for users that have been provisioned in OCS. Each tenant can have one or more identity providers. Each user is either assigned one of the available identity providers in the tenant or chooses one in the Home Realm Discovery page when accepting the invitation. A user can only log in with the same identity provider they signed up with.

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
## List Tenant Identity Providers

<a id="opIdIdentityProviders_List Tenant Identity Providers"></a>

Gets all identity providers from a tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_list-tenant-identity-providers-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of identity providers to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of identity providers to return.<br/><br/>

<h3 id="identityproviders_list-tenant-identity-providers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)[]|Identity providers found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Identity Providers Header

<a id="opIdIdentityProviders_Get Tenant Identity Providers Header"></a>

Returns the total number of identity providers in a tenant. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_get-tenant-identity-providers-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="identityproviders_get-tenant-identity-providers-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity provider headers for tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Add Tenant Identity Provider

<a id="opIdIdentityProviders_Add Tenant Identity Provider"></a>

Adds an existing identity provider to a tenant. This identity provider will be available in the Home Realm Discovery Page for users to log in or sign up.

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

<h3 id="identityproviders_add-tenant-identity-provider-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="identityproviders_add-tenant-identity-provider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProvider](#schemaidentityprovider)|Identity provider created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity provider already exists in tenant.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Identity Provider

<a id="opIdIdentityProviders_Get Tenant Identity Provider"></a>

Gets an identity provider from a tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_get-tenant-identity-provider-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_get-tenant-identity-provider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Identity Provider Header

<a id="opIdIdentityProviders_Get Tenant Identity Provider Header"></a>

Validates that a identity provider exists in the tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_get-tenant-identity-provider-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_get-tenant-identity-provider-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for identity provider.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity provider or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Remove Tenant Identity Provider

<a id="opIdIdentityProviders_Remove Tenant Identity Provider"></a>

Removes an identity provider from a tenant. Users provisioned with this identity provider will remain in the tenant, but will not be able to authenticate. An administrator cannot remove the identity provider they are signed in with.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_remove-tenant-identity-provider-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_remove-tenant-identity-provider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
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
## Get Tenant Identity Provider Consent

<a id="opIdIdentityProviders_Get Tenant Identity Provider Consent"></a>

Gets the consent information for an identity provider for a tenant. The ConsentState property, if returned, determines whether an identity provider consents to sharing access to its directory with the OCS tenant. For example, the expected ConsentState's for AAD include (Pending_)SignIn and (Pending_)ReadAllUsersGroups.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_get-tenant-identity-provider-consent-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier to check for consent.<br/><br/>

<h3 id="identityproviders_get-tenant-identity-provider-consent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity provider consent.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Tenant Identity Provider Consent Header

<a id="opIdIdentityProviders_Get Tenant Identity Provider Consent Header"></a>

Validates that a identity provider consent exists in the tenant. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_get-tenant-identity-provider-consent-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier to check for consent.<br/><br/>

<h3 id="identityproviders_get-tenant-identity-provider-consent-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Ok if the identity provider consent exists.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update Tenant Identity Provider Consent

<a id="opIdIdentityProviders_Update Tenant Identity Provider Consent"></a>

Updates the identity provider consent of a tenant. Currently only supports AAD. The consent grants User.Read.All and GroupMember.Read.All permissions to the OCS tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

### Request Body

Identity provider consent.<br/>

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}
```

<h3 id="identityproviders_update-tenant-identity-provider-consent-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier to activate consent.<br/><br/>

<h3 id="identityproviders_update-tenant-identity-provider-consent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity provider consent.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Groups

<a id="opIdIdentityProviders_Get Identity Provider Groups"></a>

Gets a list of groups that matches the query string on an identity provider that supports Advanced Integration, such as AAD. The prerequisite is that the identity provider must have already consented to sharing access to its directory with the OCS tenant. The consent grants User.Read.All and GroupMember.Read.All permissions to the OCS tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups
```

<h3 id="identityproviders_get-identity-provider-groups-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string query`<br/>Start of user name or email to search for.<br/><br/>
`[optional] integer count`<br/>Maximum number of groups to return.<br/><br/>`[optional] string skipToken`<br/>An encoded string that identifies the set of groups that was not returned. For example, if you specify a count of the first 5 groups matching your query, the skipToken identifies the 6th group.<br/><br/>

<h3 id="identityproviders_get-identity-provider-groups-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Groups By Ids

<a id="opIdIdentityProviders_Get Identity Provider Groups By Ids"></a>

Gets the groups based on the Ids. Currently, AAD provider is the only provider that supports this endpoint.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Groups
```

### Request Body

Group unique identifier list.<br/>

```json
[
  "string"
]
```

<h3 id="identityproviders_get-identity-provider-groups-by-ids-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>

<h3 id="identityproviders_get-identity-provider-groups-by-ids-responses">Responses</h3>

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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Members In A Group

<a id="opIdIdentityProviders_Get Identity Provider Members In A Group"></a>

Gets a list of all users belonging to a specific group on an identity provider that supports Advanced Integration, such as AAD. The prerequisite is that the identity provider must have already consented to sharing access to its directory with the OCS tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups/{groupId}/members
```

<h3 id="identityproviders_get-identity-provider-members-in-a-group-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string groupId`<br/>Group unique identifier.<br/><br/>
`[optional] integer count`<br/>Maximum number of users to return.<br/><br/>`[optional] string skipToken`<br/>An encoded string that identifies the set of users that was not returned. For example, if you request a count of the first 50 users matching your query, the skipToken identifies the 51st user.<br/><br/>

<h3 id="identityproviders_get-identity-provider-members-in-a-group-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderMembers](#schemaidentityprovidermembers)|List of members.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Users

<a id="opIdIdentityProviders_Get Identity Provider Users"></a>

Gets a list of users that matches the query string on an identity provider that supports Advanced Integration, such as AAD. The prerequisite is that the identity provider must have already consented to sharing access to its directory with the OCS tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/users
```

<h3 id="identityproviders_get-identity-provider-users-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string query`<br/>Start of user name or email to search for.<br/><br/>
`[optional] integer count`<br/>Maximum number of users to returns.<br/><br/>`[optional] string skipToken`<br/>An encoded string that identifies the set of users that was not returned. For example, if you specify a count of the first 50 users matching your query, the skipToken identifies the 51st user.<br/><br/>

<h3 id="identityproviders_get-identity-provider-users-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderUser](#schemaidentityproviderresultsofidentityprovideruser)|List of users found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Identity Provider Groups For User

<a id="opIdIdentityProviders_Get Identity Provider Groups For User"></a>

Gets a list of all groups that the specified user belongs to on an identity provider that supports Advanced Integration, such as AAD. The prerequisite is that the identity provider must have already consented to sharing access to its directory with the OCS tenant. The consent grants User.Read.All and GroupMember.Read.All permissions to the OCS tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Users/{userId}/Groups
```

<h3 id="identityproviders_get-identity-provider-groups-for-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string identityProviderId`<br/>Identity provider unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>
`[optional] integer skip`<br/>Indexes into a result set.<br/><br/>`[optional] integer count`<br/>Maximum number of groups to return.<br/><br/>`[optional] integer timeout`<br/>The maximum time to allow for searching groups before returning the groups.<br/><br/>`[optional] string skipToken`<br/>An encoded string that identifies the set of groups that was not returned. For example, if you request a count of the first 3 groups matching your query, the skipToken identifies the 4th user.<br/><br/>

<h3 id="identityproviders_get-identity-provider-groups-for-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups user is a member of.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity provider or tenant not found.|
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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}
```

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

The model for an identity provider consent in identity storage.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Scheme|string|false|true|Scheme of the identity provider.|

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

Object for adding an identity provider.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|email|false|true|Email address to send consent.|
|AzureActiveDirectoryConsentGivenName|string|false|true|Preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string|false|true|Preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string|false|true|AAD tenant domain name (for example, mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string|false|true|Semicolon delimited AAD consent types. Can be "SignIn" or "SignIn;ReadAllUsersGroups".|
|IdentityProviderId|guid|false|false|Identity provider unique identifier.|
|AzureActiveDirectorySendConsent|boolean|false|false|Whether to send consent email for AAD.|

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

|Property Name|Data Type|Required|Nullable|Description|
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

|Property Name|Data Type|Required|Nullable|Description|
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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}

```

Result object for Identity Provider access users/groups.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
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
  "Email": "user@example.com",
  "IsClusterManagementAllowed": true
}

```

Base class for Identity Provider access group.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|false|Gets or sets the Object Id of IdentityProviderGroup.|
|Name|string|false|true|Gets or sets group name of IdentityProviderGroup.|
|Email|email|false|true|Gets or sets the email address of the IdentityProviderGroup.|
|IsClusterManagementAllowed|boolean|false|true|Gets or sets whether group can manage cluster roles.|

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
      "Email": "user@example.com",
      "IsClusterManagementAllowed": true
    }
  ],
  "SkipToken": "string"
}

```

Class to hold members in a group.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Users|[[IdentityProviderUser](#schemaidentityprovideruser)]|false|false|List of users.|
|Groups|[[IdentityProviderGroup](#schemaidentityprovidergroup)]|false|false|List of groups.|
|SkipToken|string|false|true|Skip token for paging.|

