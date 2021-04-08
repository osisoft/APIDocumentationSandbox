---
title: Identity/communities-users v20210407.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Users
APIs for getting, updating, and deleting Users from Communities.

## List Users of a Tenant in a Community

<a id="opIdUsers_List Users of a Tenant in a Community"></a>

Get Users associated with a specific Tenant and Community.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/Users
?query={query}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant. Tenant must belong to the Community.<br/><br/>`string communityId`
<br/>The identifier of the Community.<br/><br/>
`[optional] string query`
<br/>Query to execute. Currently not supported.<br/><br/>`[optional] integer skip`
<br/>Number of records to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of records to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)[]|Set of Users (Type `User`) associated with the Tenant ( `tenantId`) and Community ( `communityId`).|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Community roles not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
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
```

### Authorization

Allowed for these roles: 
<ul>
<li>Community Member</li>
</ul>

---

## Get count of Users of a Tenant in a Community

<a id="opIdUsers_Get count of Users of a Tenant in a Community"></a>

Get the count of Users of the Tenant in this Community. This endpoint is identical to the `Int32)` endpoint except it does not return a body.

### Request
```text 
HEAD /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/Users
```

#### Parameters

`string tenantId`
<br/>Id of the calling Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Community roles not found.|
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
<li>Community Member</li>
</ul>

---

## Add User to a Community

<a id="opIdUsers_Add User to a Community"></a>

Add a User to a Community, providing a List of Community Role Ids to be assigned to the User.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/Users/{userId}
```

#### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string userId`
<br/>Id of the User to add to the specified Community.<br/><br/>

### Request Body

List of Community Roles Ids to assign to the User.<br/>

```json
[
  "string"
]
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Ok.|
|201|[User](#schemauser)|Created.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
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

Allowed for these roles: 
<ul>
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

---

## Remove User from a Community

<a id="opIdUsers_Remove User from a Community"></a>

Remove a User from a Community.

### Request
```text 
DELETE /api/v1-preview/Tenants/{tenantId}/Communities/{communityId}/Users/{userId}
```

#### Parameters

`string tenantId`
<br/>Id of the Tenant that belongs to this Community.<br/><br/>`string communityId`
<br/>Id of Community.<br/><br/>`string userId`
<br/>Id of the user to remove from the specified Community.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Removed.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
<li>Community Administrator</li>
<li>Community Moderator</li>
</ul>

---
# Definitions

## User

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

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

