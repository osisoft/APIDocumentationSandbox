

# Log
APIs related to querying logs.

## `List Tenant Logs`

<a id="opIdLog_List Tenant Logs"></a>

Get logs for a **Tenant**.

### Request
```text 
GET /api/v1/tenants/{tenantId}/logs
?start={start}&end={end}&source={source}&severity={severity}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of the tenant.<br/><br/>
`[optional] string start`
<br/>Start timestamp of logs.<br/><br/>`[optional] string end`
<br/>End timestamp of logs.<br/><br/>`[optional] array source`
<br/>Filter the logs by one or more sources. This parameter can be repeated multiple times. Valid sources are: *Account Management* and *Identity Management*. Omit this parameter to retrieve all sources. Source values must be alphanumeric (case insensitive), underscore, and whitespace only, between 1 and 50 characters<br/><br/>`[optional] array severity`
<br/>Filter the logs by one or more severities. This parameter can be repeated multiple times. Valid severities are: *Critical*, *Error*, *Warning*, *Information*, and *Verbose*. Omit this parameter to retrieve all severities.<br/><br/>`[optional] integer skip`
<br/>Number of logs to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of logs to return.<br/><br/>

#### Enumerated Values

|Parameter|Value|
|---|---|
|severity|0|
|severity|1|
|severity|2|
|severity|3|
|severity|4|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CustomerLogEntry](#schemacustomerlogentry)[]|Customer facing logs for specified tenant.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|None|Unauthorized|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Message": "string",
    "Timestamp": "2019-08-24T14:15:22Z",
    "Severity": 0,
    "Source": "string",
    "OperationId": "string",
    "EventId": 0
  }
]
```

---

## `List Namespace Logs`

<a id="opIdLog_List Namespace Logs"></a>

Get logs for a **Namespace**.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/logs
?start={start}&end={end}&source={source}&severity={severity}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of the tenant.<br/><br/>`string namespaceId`
<br/>Id of the namespace.<br/><br/>
`[optional] string start`
<br/>Start timestamp of logs.<br/><br/>`[optional] string end`
<br/>End timestamp of logs.<br/><br/>`[optional] array source`
<br/>Filter the logs by one or more sources. This parameter can be repeated multiple times. Valid sources are: *Data Ingress*, *Data Storage*, *Data Views*, *Metadata*, *PI to OCS*. Omit this parameter to retrieve all sources. Source values must be alphanumeric (case insensitive), underscore, and whitespace only, between 1 and 50 characters<br/><br/>`[optional] array severity`
<br/>Filter the logs by one or more severities. This parameter can be repeated multiple times. Valid severities are: *Critical*, *Error*, *Warning*, *Information*, and *Verbose*. Omit this parameter to retrieve all severities.<br/><br/>`[optional] integer skip`
<br/>Number of logs to skip.<br/><br/>`[optional] integer count`
<br/>Maximum number of logs to return.<br/><br/>

#### Enumerated Values

|Parameter|Value|
|---|---|
|severity|0|
|severity|1|
|severity|2|
|severity|3|
|severity|4|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[CustomerLogEntry](#schemacustomerlogentry)[]|Customer facing logs for specified tenant.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|None|Unauthorized|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  {
    "Message": "string",
    "Timestamp": "2019-08-24T14:15:22Z",
    "Severity": 0,
    "Source": "string",
    "OperationId": "string",
    "EventId": 0
  }
]
```

---
## Definitions

### CustomerLogEntry

<a id="schemacustomerlogentry"></a>
<a id="schema_CustomerLogEntry"></a>
<a id="tocScustomerlogentry"></a>
<a id="tocscustomerlogentry"></a>

Object representing a log entry returned as a stream when getting customer logs.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Message|string|true|false|Gets or sets the log message.|
|Timestamp|date-time|true|false|Gets or sets the Timestamp of the log.|
|Severity|[SeverityLevel](#schemaseveritylevel)|true|false|Gets or sets the Severity of the log.|
|Source|string|true|false|Gets or sets the Source of the log.|
|OperationId|string|true|false|Gets or sets the Operation Id of the request.|
|EventId|int32|true|false|Gets or sets the Event Id of the log.|

```json
{
  "Message": "string",
  "Timestamp": "2019-08-24T14:15:22Z",
  "Severity": 0,
  "Source": "string",
  "OperationId": "string",
  "EventId": 0
}

```

---

### SeverityLevel

<a id="schemaseveritylevel"></a>
<a id="schema_SeverityLevel"></a>
<a id="tocSseveritylevel"></a>
<a id="tocsseveritylevel"></a>

Object describing the Severity Level of customer logs.

#### Enumerated Values

|Property|Value|
|---|---|
|Verbose|0|
|Information|1|
|Warning|2|
|Error|3|
|Critical|4|

---

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Object returned when there is an error within an API request.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets the Operation Id of the action that caused the Error.|
|Error|string|true|false|Gets or sets Error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|
|Parameters|object|true|false|Gets additional properties.|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": null,
    "property2": null
  }
}

```

---

