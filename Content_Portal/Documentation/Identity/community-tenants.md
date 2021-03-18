---
title: Identity/community-tenants v20210317.1
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

# Community Tenants
APIs for getting Member Tenants info in a Community.

## Update Community Tenant By Id

<a id="opIdCommunityTenants_Update Community Tenant By Id"></a>

Updates the state of a Community Tenant. It can be activated, paused, or removed.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/communities/{communityId}/communitytenants/{communityTenantId}

```

### Request Body

The community tenant object that contains the attributes to use for the update.<br/>

```json
{
  "Status": "Undefined"
}
```

### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>`string communityTenantId`
<br/>The target community tenant in the the community to update.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|204|None|None|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Tenant Administrator</li>
</ul>

---

## Update Community Tenant By Id2

<a id="opIdCommunityTenants_Update Community Tenant By Id2"></a>

Updates the state of a Community Tenant. It can be activated, paused, or removed.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/communities/{communityId}/membertenants/{communityTenantId}

```

### Request Body

The community tenant object that contains the attributes to use for the update.<br/>

```json
{
  "Status": "Undefined"
}
```

### Parameters

`string tenantId`
<br/>The id of the owning tenant.<br/><br/>`string communityId`
<br/>The id of the community.<br/><br/>`string communityTenantId`
<br/>The target community tenant in the the community to update.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|204|None|None|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Tenant Administrator</li>
</ul>

---
# Definitions

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

## UpdateCommunityTenantInput

<a id="schemaupdatecommunitytenantinput"></a>
<a id="schema_UpdateCommunityTenantInput"></a>
<a id="tocSupdatecommunitytenantinput"></a>
<a id="tocsupdatecommunitytenantinput"></a>

The UpdateCommunityTenantInput Data Transfer Object. This is the model input for the UpdateCommunityTenantById controller endpoint.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Status|[CommunityTenantStatus](#schemacommunitytenantstatus)|false|false|The new status of the CommunityTenant in Community.|

```json
{
  "Status": "Undefined"
}

```

---

## CommunityTenantStatus

<a id="schemacommunitytenantstatus"></a>
<a id="schema_CommunityTenantStatus"></a>
<a id="tocScommunitytenantstatus"></a>
<a id="tocscommunitytenantstatus"></a>

Represents a status of a Community Tenant.

#### Enumerated Values

|Property|Value|
|---|---|
|Undefined|Undefined|
|AwaitingConfirmation|AwaitingConfirmation|
|Paused|Paused|
|Active|Active|
|Remove|Remove|

---

