

<h1 id="identity-storage-controllers-api-tenants-users-users-users">Users</h1>

## Get Users

<a id="opIdUsers_Get Users"></a>

Get a list of users from a Tenant. 
Optionally, get a list of requested users. Total number of users in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_get-users-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of User Ids to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.<br/><br/>

<h3 id="users_get-users-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)s|List of Users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of Users found.|
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
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Cloud Connect Provisioner</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Users Header

<a id="opIdUsers_Get Users Header"></a>

Return total number of users in a Tenant. Optionally, check based on a list of requested users. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_get-users-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of User Ids.<br/><br/>

<h3 id="users_get-users-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|User Header found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Cloud Connect Provisioner</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Create User

<a id="opIdUsers_Create User"></a>

Create a User in the Tenant. This endpoint does not create an invitation for the User. You will need to create an invitation in the respective endpoint for this User, otherwise they will not be able to finish the sign-up process. Users have unique Ids in a Tenant. Currently there is a limit of 50000 users per Tenant. For Windows Active Directory users, the externalUserId must be specified.

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

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="users_create-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or the User limit exceeded for Tenant.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Cloud Connect Provisioner</li>
<li>Cluster Operator</li>
</ul>

## Get User Model

<a id="opIdUsers_Get User Model"></a>

Get a User from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_get-user-model-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_get-user-model-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|User specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "1": {
    "value": {
      "Id": "00000000-0000-0000-0000-000000000001",
      "GivenName": "Name1",
      "Surname": "Surname1",
      "Name": "Name1",
      "Email": "user1@company.com",
      "ContactEmail": "user1@company.com",
      "ContactGivenName": "Name1",
      "ContactSurname": "Surname1",
      "ExternalUserId": "ExternalUserId1",
      "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
      "RoleIds": [
        "00000000-0000-0000-0000-000000000000",
        "00000000-0000-0000-0000-000000000000"
      ]
    }
  },
  "2": {
    "value": {
      "Id": "00000000-0000-0000-0000-000000000002",
      "GivenName": "Name2",
      "Surname": "Surname2",
      "Name": "Name2",
      "Email": "user2@company.com",
      "ContactEmail": "user2@company.com",
      "ContactGivenName": "Name2",
      "ContactSurname": "Surname2",
      "ExternalUserId": "ExternalUserId2",
      "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
      "RoleIds": [
        "00000000-0000-0000-0000-000000000000",
        "00000000-0000-0000-0000-000000000000"
      ]
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

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
<li>Self</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get User Header

<a id="opIdUsers_Get User Header"></a>

Validate that a User exists. This endpoint is identical to the GET one, but it does not return an object in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_get-user-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_get-user-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for User.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User does not exist.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Cloud Connect Provisioner</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
<li>Self</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Update User

<a id="opIdUsers_Update User"></a>

Update a User in a Tenant. The Id of a User cannot be changed.

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

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_update-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated User.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Delete User

<a id="opIdUsers_Delete User"></a>

Delete a User. Users cannot delete themselves. Deleting a User does not invalidate any of the existing access tokens, but it prevents this User from being able to authenticate in the future. Existing access tokens for the User will be valid until their expiration date. Refresh tokens on behalf of the User will no longer be valid after the User has been deleted. Deleting a user with explicit and claim role mappings will only have their explicit roles deleted. Forcibly deleting a user will delete a user completely regardless of claim role mappings.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_delete-user-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>
`[optional] boolean force`<br/>Forcibly delete a User that can remain due to claim role mappings.<br/><br/>

<h3 id="users_delete-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|No content.|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
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
</ul>

## Get User Preferences

<a id="opIdUsers_Get User Preferences"></a>

Get preferences from a User. User preferences can be any valid JSON object. A common use case is to store UI preferences for the User.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_get-user-preferences-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_get-user-preferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|User Preferences for specified User.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|422|[ErrorResponse](#schemaerrorresponse)|Unprocessable entity.|

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
<li>Self</li>
</ul>

## Get User Preferences Header

<a id="opIdUsers_Get User Preferences Header"></a>

Validate that there are preferences for a User. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_get-user-preferences-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_get-user-preferences-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified User's Preferences.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User or Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
<li>Self</li>
</ul>

## Update User Preferences

<a id="opIdUsers_Update User Preferences"></a>

Update preferences for a User.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_update-user-preferences-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_update-user-preferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Updated User Preferences.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|

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
<li>Self</li>
</ul>

## Get User Status

<a id="opIdUsers_Get User Status"></a>

Get invitation status for a User. It can be: InvitationAccepted (0), NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Status
```

<h3 id="users_get-user-status-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="users_get-user-status-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserStatus](#schemauserstatus)|User Status for User specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
<li>Self</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Get Users Status

<a id="opIdUsers_Get Users Status"></a>

Get invitation statuses for multiple users. Optionally restrict it only to users of a specific invitation status. The User status can be: InvitationAccepted (0),  NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/Status
```

<h3 id="users_get-users-status-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array id`<br/>Unordered list of User Ids to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.<br/><br/>`[optional] integer count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.<br/><br/>`[optional] array status`<br/>Only return statuses that match these values. Possible User statuses are: InvitationAccepted, NoInvitation, InvitationNotSent, InvitationSent, InvitationExpired.<br/><br/>

<h3 id="users_get-users-status-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [UserStatus](#schemauserstatus)s|List of User Statuses found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs. Test|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
<li>Account Member</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

<b>Strict Roles</b>
<ul>
<li>Account Administrator</li>
</ul>

## Create V1 Preview User

<a id="opIdUsers_Create V1 Preview User"></a>

Creates a `User` .

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

`string tenantId`<br/>Id of Tenant.<br/><br/>

<h3 id="users_create-v1-preview-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or User limit exceeded.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Cloud Connect Provisioner</li>
<li>Cluster Operator</li>
</ul>

## Update V1 Preview User

<a id="opIdUsers_Update V1 Preview User"></a>

Create or Update a User.

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

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of user.<br/><br/>

<h3 id="users_update-v1-preview-user-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated User.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

## Get V1 Preview Users By Ids

<a id="opIdUsers_Get V1 Preview Users By Ids"></a>

Returns an ordered list of User objects based on userId for a given tenant or a MultiStatusResponse with a list of User objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Ids
```

<h3 id="users_get-v1-preview-users-by-ids-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array userId`<br/>Unordered list of ids for all users to get.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Items to skip. Currently not supported.<br/><br/>`[optional] integer count`<br/>Maximum items to return. Currently not supported.<br/><br/>

<h3 id="users_get-v1-preview-users-by-ids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)s|List of Users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of Users found.|
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
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Get V1 Preview Users Status By Ids

<a id="opIdUsers_Get V1 Preview Users Status By Ids"></a>

Returns an ordered list of UserStatus objects for a given tenant or a MultiStatusResponse with a list of UserStatus objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Status/Ids
```

<h3 id="users_get-v1-preview-users-status-by-ids-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>
`[optional] array userId`<br/>Unordered list of ids for all users.<br/><br/>`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Items to skip. Currently not supported.<br/><br/>`[optional] integer count`<br/>Maximum number of items to retrieve. Currently not supported.<br/><br/>

<h3 id="users_get-v1-preview-users-status-by-ids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [UserStatus](#schemauserstatus)s|List of User Statuses found.|
|207|[UserStatusMultiStatusResponse](#schemauserstatusmultistatusresponse)|List of User Statuses found.|
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
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
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

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

# Schemas

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

Object for retrieving a User.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|Gets or sets unique User ID.|
|GivenName|string|false|true|Gets or sets given name of user.|
|Surname|string|false|true|Gets or sets surname of user.|
|Name|string|false|true|Gets or sets name of user.|
|Email|string|false|true|Gets or sets email of user.|
|ContactEmail|string|false|true|Gets or sets contact email for user. User will only be contacted through this email.|
|ContactGivenName|string|false|true|Gets or sets preferred contact name for user.|
|ContactSurname|string|false|true|Gets or sets preferred contact surname for user.|
|ExternalUserId|string|false|true|Gets or sets provider id for user. This is the unique ID we get from the Identity Provider.|
|IdentityProviderId|guid|false|true|Gets or sets Identity Provider Id used to authenticate User. Will be set once the User accepts an invitation. If not specified when sending the invitation to the User, it can be any of the Identity Provider Ids configured for this Tenant.|
|RoleIds|List of strings|false|true|Gets or sets list of strings of RoleIds.|

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
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Gets or sets operationId that resulted in this error.|
|Error|string|false|true|Gets or sets string message describing the error.|
|Reason|string|false|true|Gets or sets reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|Gets or sets list of ChildErrors.|
|Data|[[User](#schemauser)]|false|true|Gets or sets data.|

<h2 id="tocS_MultiStatusResponseChildError">MultiStatusResponseChildError</h2>

<a id="schemamultistatusresponsechilderror"></a>
<a id="schema_MultiStatusResponseChildError"></a>
<a id="tocSmultistatusresponsechilderror"></a>
<a id="tocsmultistatusresponsechilderror"></a>

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Object|[ErrorResponse](#schemaerrorresponse)|false|false|Object returned whenever there is an error.|

and

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|StatusCode|int32|false|false|Gets or sets hTTP status code.|
|ModelId|string|false|true|Gets or sets model ID.|

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

Object used when getting User status.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|InvitationStatus|[UserInvitationStatus](#schemauserinvitationstatus)|false|false|Gets or sets status of user invitation. Can be: InvitationAccepted (0), NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).|
|User|[User](#schemauser)|false|true|Gets or sets user information.|

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

Object when updating an User.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|true|Gets or sets user Id for the user. When creating a user, if User ID is not specified, one will be generated.|
|ExternalUserId|string|false|true|Gets or sets user ExternalUserId for the user. Must be specified if Identity Provider is Windows Active Directory.|
|ContactGivenName|string|false|true|Gets or sets preferred name to be used when contacting user.|
|ContactSurname|string|false|true|Gets or sets preferred surname to be used when contacting user.|
|ContactEmail|email|false|true|Gets or sets preferred contact email to be used. This does not have to be the same as the user's Identity Provider email.|
|IdentityProviderId|guid|false|true|Gets or sets Identity Provider this user will be required to use to login. If null, the Identity Provider Id will be set when creating the Invitation.|
|IdentityProviderSpecificUserId|string|false|true|Identity Provider Specific User Id. Ex. ObjectId for AD and AAD.|
|RoleIds|List of strings|false|true|Gets or sets list of strings of RoleIds.|

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
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Gets or sets operationId that resulted in this error.|
|Error|string|false|true|Gets or sets string message describing the error.|
|Reason|string|false|true|Gets or sets reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|Gets or sets list of ChildErrors.|
|Data|[[UserStatus](#schemauserstatus)]|false|true|Gets or sets data.|

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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|UserId|guid|false|true|None|
|ContactGivenName|string|false|true|None|
|ContactSurname|string|false|true|None|
|ContactEmail|email|false|true|None|
|RoleIds|List of strings|false|true|None|

