---
title: Identity/community-tenants v20210407.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Community Tenants
APIs for Updating and Removing Community Tenant information.

## Update a Community Tenant state (`communitytenants` path)

<a id="opIdCommunityTenants_Update a Community Tenant state (`communitytenants` path)"></a>

Updates the state of a Community Tenant. It can be activated, paused, or removed.

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/communities/{communityId}/communitytenants/{communityTenantId}
```

#### Parameters

`string callerTenantId`
<br/>The unique identifier of the owning Tenant.<br/><br/>`string communityId`
<br/>The unique identifier of the Community.<br/><br/>`string tenantIdtoUpdate`
<br/>The target CommunityTenant in the Community to update.<br/><br/>`string tenantId`
<br/><br/>`string communityTenantId`
<br/><br/>

### Request Body

The CommunityTenant object that contains the attributes to use for the update.<br/>

```json
{
  "Status": "None"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The CommunityTenant was updated.|
|204|None|No Content. No operation was performed.|
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
</ul>

---

## Remove a Community Tenant from a Community

<a id="opIdCommunityTenants_Remove a Community Tenant from a Community"></a>

Removes a Community Tenant from a Community.

### Request
```text 
DELETE /api/v1-preview/tenants/{tenantId}/communities/{communityId}/communitytenants/{communityTenantId}
```

#### Parameters

`string callerTenantId`
<br/>The unique identifier of the owning Tenant.<br/><br/>`string communityId`
<br/>The unique identifier of the Community.<br/><br/>`string tenantIdtoRemove`
<br/>The target CommunityTenant in the Community to remove.<br/><br/>`string tenantId`
<br/><br/>`string communityTenantId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
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
</ul>

---

## Update a Community Tenant state (`membertenants` path)

<a id="opIdCommunityTenants_Update a Community Tenant state (`membertenants` path)"></a>

Updates the state of a Community Tenant. It can be activated, paused, or removed.

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/communities/{communityId}/membertenants/{communityTenantId}
```

#### Parameters

`string callerTenantId`
<br/>The unique identifier of the owning Tenant.<br/><br/>`string communityId`
<br/>The unique identifier of the Community.<br/><br/>`string tenantIdtoUpdate`
<br/>The target CommunityTenant in the Community to update.<br/><br/>`string tenantId`
<br/><br/>`string communityTenantId`
<br/><br/>

### Request Body

The CommunityTenant object that contains the attributes to use for the update.<br/>

```json
{
  "Status": "None"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The CommunityTenant was updated.|
|204|None|No Content. No operation was performed.|
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
</ul>

---
# Definitions

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
  "Status": "None"
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
|None|None|
|AwaitingConfirmation|AwaitingConfirmation|
|Paused|Paused|
|Active|Active|
|Remove|Remove|

---

