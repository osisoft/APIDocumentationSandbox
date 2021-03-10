---
title: PITo-Ocs/agents v20210310.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="pito-ocs-agents-agents">Agents</h1>
The Agents controller is used to manage agent interaction. 

	

	

	

	

	

	

	

	

	

	

	

---
## Post

<a id="opIdAgents_Post"></a>

Post Sync route for specified `agentId`.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}
```

<h3 id="agents_post-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string namespaceId`<br/>The Namespace that the DataSources collection belongs to.<br/><br/>`string agentId`<br/>The Id of the specified on-prem agent.<br/><br/>

<h3 id="agents_post-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Sync route for specified `agentId` has been posted - OK.|
|202|None|Sync route for specified `agentId` has been posted - Accepted.|
|204|None|Sync route for specified `agentId` has been posted - No Content.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Get Capability Updates

<a id="opIdAgents_Get Capability Updates"></a>

Handle Agent Capabilities Updates.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/capabilities
```

<h3 id="agents_get-capability-updates-parameters">Parameters</h3>

`string agentId`<br/>The Id of the specified on-prem agent.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="agents_get-capability-updates-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A `Dictionary`2` object.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Post Capabilities

<a id="opIdAgents_Post Capabilities"></a>

Handle Agent Capabilities Publishing.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/capabilities
```

### Request Body

List of capabilities being published.<br/>

```json
[
  {
    "id": "string",
    "ver": 0,
    "en": true
  }
]
```

<h3 id="agents_post-capabilities-parameters">Parameters</h3>

`string agentId`<br/>The Id of the specified on-prem agent.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="agents_post-capabilities-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|A Task|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## Post Forwarded Logs

<a id="opIdAgents_Post Forwarded Logs"></a>

Post log messages from the on-prem agent to be forwarded to Application Insights.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/{agentId}/logs
```

<h3 id="agents_post-forwarded-logs-parameters">Parameters</h3>

`string agentId`<br/>The Id of the specified on-prem agent.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="agents_post-forwarded-logs-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|A Task|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

---
## List All Agents

<a id="opIdAgents_List All Agents"></a>

Get all `AgentDto` objects associated with the specified Namespace.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/sync/agents
```

<h3 id="agents_list-all-agents-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="agents_list-all-agents-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AgentDto](#schemaagentdto)[]|The requested collection of `DataSourceDto`.|
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

### Authorization

Allowed for these roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Tenant Member</li>
</ul>

# Definitions

<h2 id="tocS_AgentDto">AgentDto</h2>

<a id="schemaagentdto"></a>
<a id="schema_AgentDto"></a>
<a id="tocSagentdto"></a>
<a id="tocsagentdto"></a>

```json
{
  "Id": "string",
  "LastCommTime": "2019-08-24T14:15:22Z",
  "Version": "string",
  "Status": 0,
  "Description": "string",
  "HostName": "string",
  "PISystem": {
    "ServerId": "string",
    "Name": "string",
    "Version": "string",
    "AFServerId": "string",
    "AFName": "string",
    "AFVersion": "string",
    "LastCommunicationTime": "2019-08-24T14:15:22Z",
    "Transfers": [
      {
        "Id": "string",
        "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
        "Description": "string",
        "Status": "[",
        "LatestStreamingRead": "2019-08-24T14:15:22Z",
        "OnPremTransferStatus": "[",
        "PIPointCount": 0,
        "Metrics": null,
        "Name": "string",
        "MetadataPrivacy": "["
      }
    ]
  },
  "Namespace": "string",
  "Region": "string",
  "IsDeprecated": true
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|LastCommTime|date-time|false|false|None|
|Version|string|false|true|None|
|Status|[AgentStatus](#schemaagentstatus)|false|false|None|
|Description|string|false|true|None|
|HostName|string|false|true|None|
|PISystem|[PISystemDto](#schemapisystemdto)|false|true|None|
|Namespace|string|false|true|None|
|Region|string|false|true|None|
|IsDeprecated|boolean|false|false|None|

<h2 id="tocS_AgentStatus">AgentStatus</h2>

<a id="schemaagentstatus"></a>
<a id="schema_AgentStatus"></a>
<a id="tocSagentstatus"></a>
<a id="tocsagentstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Registering|0|
|Registered|1|
|Connected|2|
|Disconnected|3|
|Deleting|4|
|RegistrationFailed|5|
|DataSourceConnectionIssue|6|
|DataSourceSecurityIssue|7|
|Shutdown|8|
|MissingConfiguration|9|

<h2 id="tocS_PISystemDto">PISystemDto</h2>

<a id="schemapisystemdto"></a>
<a id="schema_PISystemDto"></a>
<a id="tocSpisystemdto"></a>
<a id="tocspisystemdto"></a>

```json
{
  "ServerId": "string",
  "Name": "string",
  "Version": "string",
  "AFServerId": "string",
  "AFName": "string",
  "AFVersion": "string",
  "LastCommunicationTime": "2019-08-24T14:15:22Z",
  "Transfers": [
    {
      "Id": "string",
      "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
      "Description": "string",
      "Status": 0,
      "LatestStreamingRead": "2019-08-24T14:15:22Z",
      "OnPremTransferStatus": 0,
      "PIPointCount": 0,
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ServerId|guid|false|false|None|
|Name|string|false|true|None|
|Version|string|false|true|None|
|AFServerId|guid|false|false|None|
|AFName|string|false|true|None|
|AFVersion|string|false|true|None|
|LastCommunicationTime|date-time|false|false|None|
|Transfers|[[TransferSummaryDto](#schematransfersummarydto)]|false|true|[Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability]|

<h2 id="tocS_TransferSummaryDto">TransferSummaryDto</h2>

<a id="schematransfersummarydto"></a>
<a id="schema_TransferSummaryDto"></a>
<a id="tocStransfersummarydto"></a>
<a id="tocstransfersummarydto"></a>

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "OnPremTransferStatus": 0,
  "PIPointCount": 0,
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}

```

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|HistoricalDataStartTime|date-time|false|false|None|
|Description|string|false|true|None|
|Status|[TransferStatus](#schematransferstatus)|false|false|None|
|LatestStreamingRead|date-time|false|false|None|
|OnPremTransferStatus|[TransferJobStatus](#schematransferjobstatus)|false|false|None|
|PIPointCount|int32|false|false|None|
|Metrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None|

<h2 id="tocS_TransferStatus">TransferStatus</h2>

<a id="schematransferstatus"></a>
<a id="schema_TransferStatus"></a>
<a id="tocStransferstatus"></a>
<a id="tocstransferstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|NotSet|0|
|Started|1|
|Stopped|2|

<h2 id="tocS_TransferJobStatus">TransferJobStatus</h2>

<a id="schematransferjobstatus"></a>
<a id="schema_TransferJobStatus"></a>
<a id="tocStransferjobstatus"></a>
<a id="tocstransferjobstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Idle|0|
|SendingHistoricalData|1|
|SendingStreamingData|2|
|BackfillingStreamingGap|4|
|Done|8|
|UncategorizedError|16|
|StreamingErrorConsumerRemoved|32|
|StreamingErrorUpdateQueueOverflow|64|
|StreamingErrorSignupDropped|128|
|StreamingErrorProducerRemoved|256|
|StreamingErrorUnknown|512|
|PIPointTypeChangeDetected|1024|
|CreatingStreams|2048|

<h2 id="tocS_TransferMetricsDto">TransferMetricsDto</h2>

<a id="schematransfermetricsdto"></a>
<a id="schema_TransferMetricsDto"></a>
<a id="tocStransfermetricsdto"></a>
<a id="tocstransfermetricsdto"></a>

```json
{
  "StreamingEventCountPerSecond": 0,
  "HistoricalEventCountPerSecond": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamingEventCountPerSecond|float|false|false|None|
|HistoricalEventCountPerSecond|float|false|false|None|

<h2 id="tocS_DataPrivacy">DataPrivacy</h2>

<a id="schemadataprivacy"></a>
<a id="schema_DataPrivacy"></a>
<a id="tocSdataprivacy"></a>
<a id="tocsdataprivacy"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Undefined|0|
|Medium|1|
|None|2|
|High|3|
|Low|4|

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

<h2 id="tocS_CapabilityState">CapabilityState</h2>

<a id="schemacapabilitystate"></a>
<a id="schema_CapabilityState"></a>
<a id="tocScapabilitystate"></a>
<a id="tocscapabilitystate"></a>

```json
{
  "Enabled": true
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Enabled|boolean|false|false|None|

<h2 id="tocS_Capability">Capability</h2>

<a id="schemacapability"></a>
<a id="schema_Capability"></a>
<a id="tocScapability"></a>
<a id="tocscapability"></a>

```json
{
  "id": "string",
  "ver": 0,
  "en": true
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|id|string|false|true|None|
|ver|int32|false|false|None|
|en|boolean|false|false|None|

