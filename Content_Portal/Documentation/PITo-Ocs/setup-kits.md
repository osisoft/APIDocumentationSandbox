---
title: PITo-Ocs/setup-kits v20210310.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="pito-ocs-setup-kits-setup-kits">Setup Kits</h1>

	

	

---
## Download

<a id="opIdSetupKits_Download"></a>

Return a `FileStreamResult` object with the PI to OCS Agent setup kit binary.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/setupkits/download
```

<h3 id="setupkits_download-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="setupkits_download-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|200: The setup kit binary.|
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
## Latest Agent Info

<a id="opIdSetupKits_Latest Agent Info"></a>

Return a `AgentSetupKitInfoDto` object which describes the latest available Agent setup kit.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/setupkits/LatestAgentInfo
```

<h3 id="setupkits_latest-agent-info-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="setupkits_latest-agent-info-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AgentSetupKitInfoDto](#schemaagentsetupkitinfodto)|200: Information about latest Agent setup kit.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Version": "string",
  "Description": "string",
  "MinimumSupportedAgentVersion": "string",
  "MinimumSupportedPIDAVersion": "string",
  "MinimumSupportedPIDAName": "string",
  "LastModified": "2019-08-24T14:15:22Z"
}
```

# Definitions

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

<h2 id="tocS_AgentSetupKitInfoDto">AgentSetupKitInfoDto</h2>

<a id="schemaagentsetupkitinfodto"></a>
<a id="schema_AgentSetupKitInfoDto"></a>
<a id="tocSagentsetupkitinfodto"></a>
<a id="tocsagentsetupkitinfodto"></a>

```json
{
  "Version": "string",
  "Description": "string",
  "MinimumSupportedAgentVersion": "string",
  "MinimumSupportedPIDAVersion": "string",
  "MinimumSupportedPIDAName": "string",
  "LastModified": "2019-08-24T14:15:22Z"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Version|string|false|true|None|
|Description|string|false|true|None|
|MinimumSupportedAgentVersion|string|false|true|None|
|MinimumSupportedPIDAVersion|string|false|true|None|
|MinimumSupportedPIDAName|string|false|true|None|
|LastModified|date-time|false|false|None|

