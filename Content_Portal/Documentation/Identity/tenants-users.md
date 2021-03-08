---
title: Identity/tenants-users v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-tenants-users-users">Users</h1>
Users consume resources in a tenant. They are invited by the administrator of the tenant and should already have a tenant in one of the configured identity providers for this tenant. A user is fully provisioned in OCS only after they have accepted the invitation and successfully logged in with an identity provider. OCS does not maintain user credentials, but it delegates authentication to the identity provider the user logged in with at first. Once logged in the user cannot change the identity provider it signed up with. A tenant can only have one user with a given email to an identity provider. If a user has multiple aliases in the same identity provider, they will not be able to create multiple corresponding OCS. Users have roles associated with them. These roles determine what a user is authorized to do in the tenant. Roles are assigned to a user upon creation and can be modified by an administrator. We allow the change of some user fields and the complete deletion of a user.

Object for retrieving a user.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|guid|User unique identifier.|
|GivenName|string|Given name of the user.|
|Surname|string|Surname of the user.|
|Name|string|Name of the user.|
|Email|string|Email of the user.|
|ContactEmail|string|Contact email for the user. User will only be contacted through this email.|
|ContactGivenName|string|Preferred contact name for the user.|
|ContactSurname|string|Preferred contact surname for the user.|
|ExternalUserId|string|Provider unique identifier for the user. This is the unique identifier we get from the identity provider.|
|IdentityProviderId|guid|Identity provider unique identifier used to authenticate the user. Will be set once the user accepts an invitation. If not specified when sending the invitation to the user, it can be any of the identity provider Ids configured for this tenant.|
|RoleIds|string[]|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

	

	

	

	

	

	

	

	

	

---
## List Users

<a id="opIdUsers_List Users"></a>

Gets a list of users from a tenant. Optionally, get a list of requested users. Total number of users in the tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_list-users-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of user Ids to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.<br/><br/>

<h3 id="users_list-users-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)[]|List of users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of users found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 207 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
  ]
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
## Get Users Header

<a id="opIdUsers_Get Users Header"></a>

Returns the total number of users in a tenant. Optionally, check based on a list of requested users. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_get-users-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of user Ids.<br/><br/>

<h3 id="users_get-users-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|User header found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User not found.|
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
## Create User

<a id="opIdUsers_Create User"></a>

Creates a user in the tenant. This endpoint does not create an invitation for the user. You will need to create an invitation in the respective endpoint for this user, otherwise they will not be able to finish the sign-up process. Users have unique Ids in a tenant. Currently there is a limit of 50000 users per tenant. For Windows Active Directory users, the externalUserId must be specified.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Users
```

### Request Body

UserCreateOrUpdate object.<br/>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_create-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="users_create-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or the user limit exceeded for tenant.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
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
## Get User Model

<a id="opIdUsers_Get User Model"></a>

Gets a user from tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_get-user-model-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_get-user-model-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|User specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get User Header

<a id="opIdUsers_Get User Header"></a>

Validates that a user exists. This endpoint is identical to the GET one, but it does not return an object in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_get-user-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_get-user-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for user.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User does not exist.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update User

<a id="opIdUsers_Update User"></a>

Updates a user in a tenant. The user unique identifier cannot be changed.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}
```

### Request Body

UserCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_update-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_update-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated user.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
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
## Delete User

<a id="opIdUsers_Delete User"></a>

Deletes a user. Users cannot delete themselves. Deleting a user does not invalidate any of the existing access tokens, but it prevents this user from being able to authenticate in the future. Existing access tokens for the user will be valid until their expiration date. Refresh tokens on behalf of the user will no longer be valid after the user has been deleted. Deleting a user with explicit and claim role mappings will only have their explicit roles deleted. Forcibly deleting a user will delete a user completely regardless of claim role mappings.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_delete-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>
`[optional] boolean force`<br/>Forcibly delete a user that can remain due to claim role mappings.<br/><br/>

<h3 id="users_delete-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|No content.|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
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
## Get User Preferences

<a id="opIdUsers_Get User Preferences"></a>

Gets preferences from a user. User preferences can be any valid JSON object. A common use case is to store UI preferences for the user.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_get-user-preferences-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_get-user-preferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|User preferences for specified user.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|422|[ErrorResponse](#schemaerrorresponse)|Unprocessable entity.|

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
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---
## Get User Preferences Header

<a id="opIdUsers_Get User Preferences Header"></a>

Validates that there are preferences for a user. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_get-user-preferences-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_get-user-preferences-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified user's preferences.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---
## Update User Preferences

<a id="opIdUsers_Update User Preferences"></a>

Updates preferences for a user.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_update-user-preferences-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_update-user-preferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Updated user preferences.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|

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
<li>Self</li>
<li>Tenant Administrator</li>
</ul>

---
## Get User Status

<a id="opIdUsers_Get User Status"></a>

Gets invitation status for a user. It can be: InvitationAccepted (0), NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Status
```

<h3 id="users_get-user-status-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_get-user-status-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserStatus](#schemauserstatus)|User status for user specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "InvitationStatus": 0,
  "User": {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Self</li>
<li>Tenant Member</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## List Users Status

<a id="opIdUsers_List Users Status"></a>

Gets invitation statuses for multiple users. Optionally restrict it only to users of a specific invitation status. The user status can be: InvitationAccepted (0), NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/Status
```

<h3 id="users_list-users-status-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array id`<br/>Unordered list of user Ids to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.<br/><br/>`[optional] array status`<br/>Only return statuses that match these values. Possible user statuses are: InvitationAccepted, NoInvitation, InvitationNotSent, InvitationSent, InvitationExpired.<br/><br/>

<h3 id="users_list-users-status-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserStatus](#schemauserstatus)[]|List of user statuses found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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

<b>Strict Roles</b>
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Create V1 Preview User

<a id="opIdUsers_Create V1 Preview User"></a>

Creates a `User`.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/Users
```

### Request Body

User values to use during creating.<br/>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_create-v1-preview-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>

<h3 id="users_create-v1-preview-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or user limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
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
## Update V1 Preview User

<a id="opIdUsers_Update V1 Preview User"></a>

Create or Update a user.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/Users/{userId}
```

### Request Body

A UserStatus object.<br/>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_update-v1-preview-user-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="users_update-v1-preview-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated user.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
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
## List V1 Preview Users By Ids

<a id="opIdUsers_List V1 Preview Users By Ids"></a>

Returns an ordered list of user objects based on userId for a given tenant or a MultiStatusResponse with a list of user objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Ids
```

<h3 id="users_list-v1-preview-users-by-ids-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array userId`<br/>Unordered list of Ids for all users to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Items to skip. Currently not supported.<br/><br/>`[optional] integer count`<br/>Maximum items to return. Currently not supported.<br/><br/>

<h3 id="users_list-v1-preview-users-by-ids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)[]|List of users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of users found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 207 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
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
## List V1 Preview Users Status By Ids

<a id="opIdUsers_List V1 Preview Users Status By Ids"></a>

Returns an ordered list of UserStatus objects for a given tenant or a MultiStatusResponse with a list of UserStatus objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Status/Ids
```

<h3 id="users_list-v1-preview-users-status-by-ids-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] array userId`<br/>Unordered list of Ids for all users.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Items to skip. Currently not supported.<br/><br/>`[optional] integer count`<br/>Maximum number of items to retrieve. Currently not supported.<br/><br/>

<h3 id="users_list-v1-preview-users-status-by-ids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserStatus](#schemauserstatus)[]|List of user statuses found.|
|207|[UserStatusMultiStatusResponse](#schemauserstatusmultistatusresponse)|List of user statuses found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body
> 207 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "InvitationStatus": 0,
      "User": {
        "Id": "string",
        "GivenName": "string",
        "Surname": "string",
        "Name": "string",
        "Email": "string",
        "ContactEmail": "string",
        "ContactGivenName": "string",
        "ContactSurname": "string",
        "ExternalUserId": "string",
        "IdentityProviderId": "string",
        "RoleIds": [
          null
        ]
      }
    }
  ]
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_User">User</h2>

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object for retrieving a user.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|User unique identifier.|
|GivenName|string|false|true|Given name of the user.|
|Surname|string|false|true|Surname of the user.|
|Name|string|false|true|Name of the user.|
|Email|string|false|true|Email of the user.|
|ContactEmail|string|false|true|Contact email for the user. User will only be contacted through this email.|
|ContactGivenName|string|false|true|Preferred contact name for the user.|
|ContactSurname|string|false|true|Preferred contact surname for the user.|
|ExternalUserId|string|false|true|Provider unique identifier for the user. This is the unique identifier we get from the identity provider.|
|IdentityProviderId|guid|false|true|Identity provider unique identifier used to authenticate the user. Will be set once the user accepts an invitation. If not specified when sending the invitation to the user, it can be any of the identity provider Ids configured for this tenant.|
|RoleIds|string[]|false|true|List of roles to be assigned to this client. Member role is always required. For security reasons we advise against assigning administrator role to a client.|

<h2 id="tocS_UserMultiStatusResponse">UserMultiStatusResponse</h2>

<a id="schemausermultistatusresponse"></a>
<a id="schema_UserMultiStatusResponse"></a>
<a id="tocSusermultistatusresponse"></a>
<a id="tocsusermultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
  ]
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Operation unique identifier that resulted in this error.|
|Error|string|false|true|Message describing the error.|
|Reason|string|false|true|Reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|List of child errors.|
|Data|[[User](#schemauser)]|false|true|Data representing users.|

<h2 id="tocS_MultiStatusResponseChildError">MultiStatusResponseChildError</h2>

<a id="schemamultistatusresponsechilderror"></a>
<a id="schema_MultiStatusResponseChildError"></a>
<a id="tocSmultistatusresponsechilderror"></a>
<a id="tocsmultistatusresponsechilderror"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "StatusCode": 0,
  "ModelId": "string",
  "property1": null,
  "property2": null
}

```

ChildError objects returned in a 207 response.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Operation unique identifier of action that caused the error.|
|Error|string|true|false|Error description.|
|Reason|string|true|false|Reason for the error.|
|Resolution|string|true|false|Resolution needed to resolve the Error.|
|StatusCode|int32|false|false|Http status code.|
|ModelId|string|false|true|Model Id.|

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

<h2 id="tocS_UserStatus">UserStatus</h2>

<a id="schemauserstatus"></a>
<a id="schema_UserStatus"></a>
<a id="tocSuserstatus"></a>
<a id="tocsuserstatus"></a>

```json
{
  "InvitationStatus": 0,
  "User": {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
}

```

Object used when getting user status.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|InvitationStatus|[UserInvitationStatus](#schemauserinvitationstatus)|false|false|Status of user invitation. Can be: InvitationAccepted (0), NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).|
|User|[User](#schemauser)|false|true|User information.|

<h2 id="tocS_UserInvitationStatus">UserInvitationStatus</h2>

<a id="schemauserinvitationstatus"></a>
<a id="schema_UserInvitationStatus"></a>
<a id="tocSuserinvitationstatus"></a>
<a id="tocsuserinvitationstatus"></a>

User Invitation Status.

#### Enumerated Values

|Property|Value|
|---|---|
|InvitationAccepted|0|
|NoInvitation|1|
|InvitationNotSent|2|
|InvitationSent|3|
|InvitationExpired|4|

<h2 id="tocS_UserCreateOrUpdate">UserCreateOrUpdate</h2>

<a id="schemausercreateorupdate"></a>
<a id="schema_UserCreateOrUpdate"></a>
<a id="tocSusercreateorupdate"></a>
<a id="tocsusercreateorupdate"></a>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object when updating a user.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|true|User unique identifier. When creating a user, if user unique identifier is not specified, one will be generated.|
|ExternalUserId|string|false|true|User ExternalUserId for the user. Must be specified if the identity provider is Windows Active Directory.|
|ContactGivenName|string|false|true|Preferred name to be used when contacting user.|
|ContactSurname|string|false|true|Preferred surname to be used when contacting user.|
|ContactEmail|email|false|true|Preferred contact email to be used. This does not have to be the same as the user's identity provider email.|
|IdentityProviderId|guid|false|true|Identity provider this user will be required to use to log in. If null, the identity provider unique identifier will be set when creating the invitation.|
|IdentityProviderSpecificUserId|string|false|true|Identity provider specific user unique identifier. For example, object Id for AD and AAD.|
|RoleIds|string[]|false|true|List of strings of role Ids.|

<h2 id="tocS_UserStatusMultiStatusResponse">UserStatusMultiStatusResponse</h2>

<a id="schemauserstatusmultistatusresponse"></a>
<a id="schema_UserStatusMultiStatusResponse"></a>
<a id="tocSuserstatusmultistatusresponse"></a>
<a id="tocsuserstatusmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "InvitationStatus": 0,
      "User": {
        "Id": "string",
        "GivenName": "string",
        "Surname": "string",
        "Name": "string",
        "Email": "string",
        "ContactEmail": "string",
        "ContactGivenName": "string",
        "ContactSurname": "string",
        "ExternalUserId": "string",
        "IdentityProviderId": "string",
        "RoleIds": [
          null
        ]
      }
    }
  ]
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Operation unique identifier that resulted in this error.|
|Error|string|false|true|Message describing the error.|
|Reason|string|false|true|Reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|List of child errors.|
|Data|[[UserStatus](#schemauserstatus)]|false|true|Data representing user statuses.|

<h2 id="tocS_UserCreateOrUpdate2">UserCreateOrUpdate2</h2>

<a id="schemausercreateorupdate2"></a>
<a id="schema_UserCreateOrUpdate2"></a>
<a id="tocSusercreateorupdate2"></a>
<a id="tocsusercreateorupdate2"></a>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|UserId|guid|false|true|None|
|ContactGivenName|string|false|true|None|
|ContactSurname|string|false|true|None|
|ContactEmail|email|false|true|None|
|RoleIds|string[]|false|true|None|

