---
title: PITo-Ocs/maintenance v20210310.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="pito-ocs-maintenance-maintenance">Maintenance</h1>

	

	

	

---
## Get Data Source Owner For Agent

<a id="opIdMaintenance_Get Data Source Owner For Agent"></a>

Internal-Only method for looking up a DataSource `Trustee` object, using a specified `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pitoocs/maintenance/{agentId}/dataSourceOwner
```

<h3 id="maintenance_get-data-source-owner-for-agent-parameters">Parameters</h3>

`string agentId`<br/>The Id of the Agent that belongs to the desired DataSource.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="maintenance_get-data-source-owner-for-agent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|A `Trustee` representing the owner of the agent's DataSource.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

---
## Verify Namespace Scoped Resources Consistent

<a id="opIdMaintenance_Verify Namespace Scoped Resources Consistent"></a>

Verify that all agent resources associated with the specified `namespaceId` exist.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pitoocs/maintenance/NamespaceScopedResources
```

<h3 id="maintenance_verify-namespace-scoped-resources-consistent-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace that the agent resource belongs to.<br/><br/>

<h3 id="maintenance_verify-namespace-scoped-resources-consistent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|204: No Content - when resources are consistent and 200: OK - returns a list of inconsistent resources|
|204|None|204: No Content - when resources are consistent and 200: OK - returns a list of inconsistent resources|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Update Namespace Scoped Resources

<a id="opIdMaintenance_Update Namespace Scoped Resources"></a>

Update all agent resources associated with the specified `namespaceId` to be consistent with Agent Status

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pitoocs/maintenance/NamespaceScopedResources
```

<h3 id="maintenance_update-namespace-scoped-resources-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace that the agent resource belongs to.<br/><br/>

<h3 id="maintenance_update-namespace-scoped-resources-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|All agent resources associated with the specified `namespaceId` were updated to be consistent with agent status.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Delete Namespace Scoped Resources

<a id="opIdMaintenance_Delete Namespace Scoped Resources"></a>

Delete all agent resources associated with the specified `namespaceId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pitoocs/maintenance/NamespaceScopedResources
```

<h3 id="maintenance_delete-namespace-scoped-resources-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace that the agent resource belongs to.<br/><br/>

<h3 id="maintenance_delete-namespace-scoped-resources-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|204: No content|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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

# Definitions

<h2 id="tocS_Trustee">Trustee</h2>

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[TrusteeType](#schematrusteetype)|false|false|None|
|ObjectId|string|false|true|None|
|TenantId|string|false|true|None|

<h2 id="tocS_TrusteeType">TrusteeType</h2>

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

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

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|

