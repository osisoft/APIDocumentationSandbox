

<h1 id="identity-storage-cloudcontrollers-api-tenants-users-invitation-invitation">Invitation</h1>

## Get User Invitation

<a id="opIdInvitation_Get User Invitation"></a>

Get Invitation for a User.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_get-user-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="invitation_get-user-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation for specified User.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation, User, or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
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

## Get User Invitation Header

<a id="opIdInvitation_Get User Invitation Header"></a>

Validate that Invitation exist for a User. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_get-user-invitation-header-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>
`[optional] boolean includeExpiredInvitations`<br/>Specify whether to include expired invitations.<br/><br/>

<h3 id="invitation_get-user-invitation-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Invitation for the specified User.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
<li>Cluster Operator</li>
<li>Cluster Support</li>
</ul>

## Create Invitation

<a id="opIdInvitation_Create Invitation"></a>

Create an Invitation for a User. Should use when no other Invitation exists for the User.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

### Request Body

InvitationCreateOrUpdate object.<br/>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}
```

<h3 id="invitation_create-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="invitation_create-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Invitation](#schemainvitation)|Invitation created.|
|202|None|Invitation created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Invitation already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
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

## Create Or Update Invitation

<a id="opIdInvitation_Create Or Update Invitation"></a>

Create or update an Invitation for a User.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

### Request Body

InvitationCreateOrUpdate object.<br/>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}
```

<h3 id="invitation_create-or-update-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="invitation_create-or-update-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation created or updated.|
|201|[Invitation](#schemainvitation)|Invitation created or updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Invitation already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
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

## Delete User Invitation

<a id="opIdInvitation_Delete User Invitation"></a>

Delete an Invitation for a User.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_delete-user-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string userId`<br/>Id of User.<br/><br/>

<h3 id="invitation_delete-user-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or Tenant not found.|
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

# Schemas

<h2 id="tocS_Invitation">Invitation</h2>

<a id="schemainvitation"></a>
<a id="schema_Invitation"></a>
<a id="tocSinvitation"></a>
<a id="tocsinvitation"></a>

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
}

```

Object for an Invitation.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets unique Invitation Id.|
|Issued|date-time|false|false|Gets or sets invitation issuing timestamp.|
|Expires|date-time|false|false|Gets or sets invitation expiration timestamp.|
|Accepted|date-time|false|true|Gets or sets invitation accepted timestamp.|
|State|[InvitationStates](#schemainvitationstates)|false|false|Gets or sets invitation state. Can be None (0), InvitationEmailSent (1), InvitationAccepted (2).|
|TenantId|guid|false|false|Gets or sets ID of the Tenant the invitation belongs to.|
|UserId|guid|false|false|Gets or sets ID of the User whom the invitation was issued to.|

<h2 id="tocS_InvitationStates">InvitationStates</h2>

<a id="schemainvitationstates"></a>
<a id="schema_InvitationStates"></a>
<a id="tocSinvitationstates"></a>
<a id="tocsinvitationstates"></a>

Invitation states.

#### Enumerated Values

|Property|Value|
|---|---|
|None|0|
|InvitationEmailSent|1|
|InvitationAccepted|2|

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

<h2 id="tocS_InvitationCreateOrUpdate">InvitationCreateOrUpdate</h2>

<a id="schemainvitationcreateorupdate"></a>
<a id="schema_InvitationCreateOrUpdate"></a>
<a id="tocSinvitationcreateorupdate"></a>
<a id="tocsinvitationcreateorupdate"></a>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}

```

Object used to create or update an Invitation.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|ExpiresDateTime|date-time|false|true|Gets or sets invitation expiration date. Must be in the future. Maximum allowed is two month in the future. Defaults to 21 days on creation. It should be in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) and either include a *Z* at the end to represent UTC timezone or include the offset in hours. If neither is present time will be treated in the local time zone of the server.|
|State|[InvitationStates](#schemainvitationstates)|false|true|Gets or sets set the state of invitation. For OSISoft internal use only.|
|SendInvitation|boolean|false|true|Gets or sets send an invitation email. Invitation will be sent to the ContactEmail in the User this invitation is attached to. Default is true.|
|IdentityProviderId|guid|false|true|Gets or sets Identity Provider to use for accepting this invitation. Required when creating an Invitation.|

