---
title: Identity/communities v20210308.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="identity-communities-communities">Communities</h1>
A Community is an organizational entity that facilitates data sharing across multiple Tenants.

	

	

	

	

	

	

---
## List Joined Communities

<a id="opIdCommunities_List Joined Communities"></a>

Gets all communities a tenant is joined to.

### Request
```text 
GET /api/v1/tenants/{tenantId}/Communities
```

<h3 id="communities_list-joined-communities-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>

<h3 id="communities_list-joined-communities-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Community](#schemacommunity)[]|Returns the current communities for the tenant. This is a set of objects of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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

---
## Create Community

<a id="opIdCommunities_Create Community"></a>

Creates a new community within a specific tenant. The tenant sending this request will be assigned ownership of the community. The calling user or client will be granted community administrator and member roles for the community.

### Request
```text 
POST /api/v1/tenants/{tenantId}/Communities
```

### Request Body

The community information to create.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3 id="communities_create-community-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>

<h3 id="communities_create-community-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Community](#schemacommunity)|Returns the created community of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|None|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Administrator</li>
</ul>

---
## Get Community By Id

<a id="opIdCommunities_Get Community By Id"></a>

Gets a community and related information by id.

### Request
```text 
GET /api/v1/tenants/{tenantId}/Communities/{communityId}
```

<h3 id="communities_get-community-by-id-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>`string communityId`<br/>The id of the community to find.<br/><br/>

<h3 id="communities_get-community-by-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Community](#schemacommunity)|Returns the current communities for the tenant. This is a set of objects of type `Community`.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|None|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}
```

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Community Member</li>
<li>Tenant Administrator</li>
</ul>

---
## Update Community By Id

<a id="opIdCommunities_Update Community By Id"></a>

Updates attributes of a community such as name and description.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/Communities/{communityId}
```

### Request Body

The community object that contains the attributes to use for the update.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3 id="communities_update-community-by-id-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>`string communityId`<br/>The id of the community.<br/><br/>

<h3 id="communities_update-community-by-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success. The community tenant was updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The requested community tenant was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Community Administrator</li>
<li>Tenant Administrator</li>
</ul>

---
## Delete Community

<a id="opIdCommunities_Delete Community"></a>

Deletes a community by id.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/Communities/{communityId}
```

<h3 id="communities_delete-community-parameters">Parameters</h3>

`string tenantId`<br/>The id of the owning tenant.<br/><br/>`string communityId`<br/>The id of the community to delete.<br/><br/>

<h3 id="communities_delete-community-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No Content. The community was successfully deleted.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request. The server could not understand the request due to invalid syntax.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized. The client has not been authenticated.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden. The client does not have the required permissions to make the request.|
|404|[ErrorResponse](#schemaerrorresponse)|Not Found. The community was not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Request Timeout. The request has timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error. The server has encountered a situation it doesn't know how to handle.|

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
<li>Community Administrator</li>
<li>Tenant Administrator</li>
</ul>

# Definitions

<h2 id="tocS_Community">Community</h2>

<a id="schemacommunity"></a>
<a id="schema_Community"></a>
<a id="tocScommunity"></a>
<a id="tocscommunity"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Alias": "string",
  "Description": "string",
  "Tenants": [
    {
      "Id": "string",
      "Name": "string",
      "Status": "Undefined",
      "IsOwner": true,
      "UserCount": 0,
      "ClientCount": 0
    }
  ],
  "DateCreated": "2019-08-24T14:15:22Z",
  "StreamsContributedCount": 0,
  "TotalStreamsContributedCount": 0
}

```

The Community Data Transfer Object. This is the model representation exposed to callers of controller endpoints.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|The Primary Key.|
|Name|string|false|true|The Name of the Community.|
|Alias|string|false|true|The requesting Tenant's alias for the Community.|
|Description|string|false|true|The Description of the Community.|
|Tenants|[[CommunityTenant](#schemacommunitytenant)]|false|true|The List of CommunityTenants that are in the Community.|
|DateCreated|date-time|false|true|The Date that the Community was created.|
|StreamsContributedCount|integer|false|false|Current Tenant's view of how many streams it contributed.|
|TotalStreamsContributedCount|integer|false|false|Total streams from all Community Tenants.|

<h2 id="tocS_CommunityTenant">CommunityTenant</h2>

<a id="schemacommunitytenant"></a>
<a id="schema_CommunityTenant"></a>
<a id="tocScommunitytenant"></a>
<a id="tocscommunitytenant"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Status": "Undefined",
  "IsOwner": true,
  "UserCount": 0,
  "ClientCount": 0
}

```

The Community Tenant Data Transfer Object.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|The Tenant ID.|
|Name|string|false|true|The name of the Tenant.|
|Status|[CommunityTenantStatus](#schemacommunitytenantstatus)|false|false|The Status of the CommunityTenant in the Community.|
|IsOwner|boolean|false|false|Boolean to indicate if CommunityTenant is Owner of Community.|
|UserCount|integer|false|false|Summary count of the users authorized to access this community within the Tenant.|
|ClientCount|integer|false|false|Summary count of the clients authorized to access this community within this Tenant.|

<h2 id="tocS_CommunityTenantStatus">CommunityTenantStatus</h2>

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

<h2 id="tocS_CreateCommunityInput">CreateCommunityInput</h2>

<a id="schemacreatecommunityinput"></a>
<a id="schema_CreateCommunityInput"></a>
<a id="tocScreatecommunityinput"></a>
<a id="tocscreatecommunityinput"></a>

```json
{
  "Name": "string",
  "Description": "string"
}

```

The CreateCommunityInput Data Transfer Object. This is the model input for the CreateCommunity controller endpoint.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|The Name of the Community to create.|
|Description|string|false|true|The Description of the Community.|

<h2 id="tocS_UpdateCommunityInput">UpdateCommunityInput</h2>

<a id="schemaupdatecommunityinput"></a>
<a id="schema_UpdateCommunityInput"></a>
<a id="tocSupdatecommunityinput"></a>
<a id="tocsupdatecommunityinput"></a>

```json
{
  "Name": "string",
  "Description": "string"
}

```

The UpdateCommunityInput Data Transfer Object. This is the model input for the UpdateCommunityById controller endpoint.

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|The Name of the Community.|
|Description|string|false|true|The Description of the Community.|

