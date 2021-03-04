---
title: Identity/tenants-invitations v20210304.3
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-tenants-invitations-invitations">Invitations</h1>
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
## List Invitations

<a id="opIdInvitations_List Invitations"></a>

Gets all non-expired invitations from a tenant. Optionally include expired invitations.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Invitations
```

<h3 id="invitations_list-invitations-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] string query`<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`<br/>Number of invitations to skip.<br/><br/>`[optional] integer count`<br/>Maximum number of invitations to return.<br/><br/>`[optional] boolean includeExpiredInvitations`<br/>Specify whether to return expired invitations.<br/><br/>

<h3 id="invitations_list-invitations-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)[]|Invitations found.|
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
<li>Tenant Administrator</li>
</ul>

---
## Get Invitations Header

<a id="opIdInvitations_Get Invitations Header"></a>

Returns the total number of non-expired invitations in a tenant. Optionally include expired invitations. The value will be set in the Total-Count header. This endpoint is identical to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Invitations
```

<h3 id="invitations_get-invitations-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>
`[optional] boolean includeExpiredInvitations`<br/>Specify to return expired invitations.<br/><br/>

<h3 id="invitations_get-invitations-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for invitations found.|
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
## Get Invitation

<a id="opIdInvitations_Get Invitation"></a>

Gets an invitation from tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_get-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string invitationId`<br/>Invitation unique identifier.<br/><br/>

<h3 id="invitations_get-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or tenant not found.|
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
## Get Invitation Header

<a id="opIdInvitations_Get Invitation Header"></a>

Validates that an invitation exists. This endpoint is identical to the GET one, but it does not return an object in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_get-invitation-header-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string invitationId`<br/>Invitation unique identifier.<br/><br/>

<h3 id="invitations_get-invitation-header-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for invitation specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Invitation or tenant not found.|
|500|None|Internal server error.|

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Update Invitation

<a id="opIdInvitations_Update Invitation"></a>

Updates an invitation. Expired invitations will not be extended. automatically upon updates.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

### Request Body

New InvitationCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}
```

<h3 id="invitations_update-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string invitationId`<br/>Invitation unique identifier.<br/><br/>

<h3 id="invitations_update-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Updated invitation.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
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
## Delete Invitation

<a id="opIdInvitations_Delete Invitation"></a>

Deletes an invitation. Users who already have an invitation email will not be able to sign up once the invitation is deleted.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_delete-invitation-parameters">Parameters</h3>

`string tenantId`<br/>Tenant unique identifier.<br/><br/>`string invitationId`<br/>Invitation unique identifier.<br/><br/>

<h3 id="invitations_delete-invitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
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

