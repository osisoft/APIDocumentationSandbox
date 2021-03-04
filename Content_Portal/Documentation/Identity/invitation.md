---
title: Identity/invitation v20210304.5
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-invitation-invitation">Invitation</h1>
Invitations are issued after the creation of a user object in OCS, to begin the provisioning process for a user with one of the identity providers in a tenant. There can only be one invitation for a user at a time. An invitation can expire, at which time the administrator can either delete it, or extend it. When creating an invitation a tenant administrator has the option to resend the invitation email to the contact email configured for the user the invitation is attached to. The email can be re-sent by updating the invitation. When an invitation expires the user cannot accept it. If the expiration date is extended the user can accept an invitation. Invitations that are past of their expiration date by more than two weeks will be deleted. The only way to provision a user after this, is to send a new invitation.

Object for an invitation.

### Properties
|Property Name|Data Type|Description|
|---|---|---|
|Id|string|Invitation unique identifier.|
|Issued|date-time|Invitation issuing timestamp.|
|Expires|date-time|Invitation expiration timestamp.|
|Accepted|date-time|Invitation accepted timestamp.|
|State|[InvitationStates](#schemainvitationstates)|Invitation state. Can be None (0), InvitationEmailSent (1), InvitationAccepted (2).|
|TenantId|guid|Unique identifier of the tenant the invitation belongs to.|
|UserId|guid|Unique identifier of the user to whom the invitation was issued.|

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

	

	

	

	

---
## Get User Invitation

<a id="opIdInvitation_Get User Invitation"></a>

Get invitation for a user.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_get-user-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="invitation_get-user-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation for specified user.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation, user, or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get User Invitation Header

<a id="opIdInvitation_Get User Invitation Header"></a>

Validate that invitation exist for a user. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_get-user-invitation-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>
`[optional] boolean includeExpiredInvitations`<br/>Specify whether to include expired invitations.<br/><br/>

<h3 id="invitation_get-user-invitation-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for invitation for the specified user.|
|400|None|Missing or invalid inputs.|
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
## Create Invitation

<a id="opIdInvitation_Create Invitation"></a>

Create an invitation for a user. Should use when no other invitation exists for the user.

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

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="invitation_create-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Invitation](#schemainvitation)|Invitation created.|
|202|None|Invitation created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Create Or Update Invitation

<a id="opIdInvitation_Create Or Update Invitation"></a>

Create or update an invitation for a user.

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

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="invitation_create-or-update-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation created or updated.|
|201|[Invitation](#schemainvitation)|Invitation created or updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or tenant not found.|
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

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Delete User Invitation

<a id="opIdInvitation_Delete User Invitation"></a>

Delete an invitation for a user.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Users/{userId}/Invitation
```

<h3 id="invitation_delete-user-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string userId`<br/>User unique identifier.<br/><br/>

<h3 id="invitation_delete-user-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or tenant not found.|
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

# Definitions

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

Object for an invitation.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Invitation unique identifier.|
|Issued|date-time|false|false|Invitation issuing timestamp.|
|Expires|date-time|false|false|Invitation expiration timestamp.|
|Accepted|date-time|false|true|Invitation accepted timestamp.|
|State|[InvitationStates](#schemainvitationstates)|false|false|Invitation state. Can be None (0), InvitationEmailSent (1), InvitationAccepted (2).|
|TenantId|guid|false|false|Unique identifier of the tenant the invitation belongs to.|
|UserId|guid|false|false|Unique identifier of the user to whom the invitation was issued.|

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

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ExpiresDateTime|date-time|false|true|Gets or sets invitation expiration date. Must be in the future. Maximum allowed is two month in the future. Defaults to 21 days on creation. It should be in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) and either include a *Z* at the end to represent UTC timezone or include the offset in hours. If neither is present time will be treated in the local time zone of the server.|
|State|[InvitationStates](#schemainvitationstates)|false|true|Gets or sets set the state of invitation. For OSISoft internal use only.|
|SendInvitation|boolean|false|true|Gets or sets send an invitation email. Invitation will be sent to the ContactEmail in the User this invitation is attached to. Default is true.|
|IdentityProviderId|guid|false|true|Gets or sets Identity Provider to use for accepting this invitation. Required when creating an Invitation.|

