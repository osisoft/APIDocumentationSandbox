---
title: Context/rule-errors v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="context-rule-errors-rule-errors">Rule Errors</h1>

	

	

	

---
## List Rule Errors By Rule Id

<a id="opIdRuleErrors_List Rule Errors By Rule Id"></a>

Gets the `RuleErrorDto` objects for the specified ruleId.

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/errors
```

<h3 id="ruleerrors_list-rule-errors-by-rule-id-parameters">Parameters</h3>

`string ruleId`<br/>The rule Id.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="ruleerrors_list-rule-errors-by-rule-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RuleErrorDto](#schemaruleerrordto)[]|An `IEnumerable`1`|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|None|

### Example response body
> 200 Response

```json
[
  {
    "Id": "00000000-0000-0000-0000-000000000000",
    "RuleId": "ruleId",
    "TimeGenerated": "0001-01-01T00:00:00",
    "ErrorDetails": "Error details.",
    "ErrorMessageType": 1
  },
  {
    "Id": "00000000-0000-0000-0000-000000000000",
    "RuleId": "ruleId",
    "TimeGenerated": "0001-01-01T00:00:00",
    "ErrorDetails": "Error details.",
    "ErrorMessageType": 1
  }
]
```

> 403 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

> 404 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

> 500 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

---
## Delete Rule Errors By Rule Id

<a id="opIdRuleErrors_Delete Rule Errors By Rule Id"></a>

Deletes the `RuleErrorDto` objects associated with the specified rule.

### Request
```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/errors
```

<h3 id="ruleerrors_delete-rule-errors-by-rule-id-parameters">Parameters</h3>

`string ruleId`<br/>The rule Id.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="ruleerrors_delete-rule-errors-by-rule-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|None|

### Example response body
> 403 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

> 404 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

> 500 Response

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

# Definitions

<h2 id="tocS_RuleErrorDto">RuleErrorDto</h2>

<a id="schemaruleerrordto"></a>
<a id="schema_RuleErrorDto"></a>
<a id="tocSruleerrordto"></a>
<a id="tocsruleerrordto"></a>

```json
{
  "Id": "00000000-0000-0000-0000-000000000000",
  "RuleId": "ruleId",
  "TimeGenerated": "0001-01-01T00:00:00",
  "ErrorDetails": "Error details.",
  "ErrorMessageType": 1
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|RuleId|string|false|true|None|
|TimeGenerated|date-time|false|false|None|
|ErrorDetails|string|false|true|None|
|ErrorMessageType|[ErrorMessageType](#schemaerrormessagetype)|false|false|None|

<h2 id="tocS_ErrorMessageType">ErrorMessageType</h2>

<a id="schemaerrormessagetype"></a>
<a id="schema_ErrorMessageType"></a>
<a id="tocSerrormessagetype"></a>
<a id="tocserrormessagetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|ConflictBetweenRules|0|
|CreateOrUpdate|1|
|Generic|2|
|AutomationId|3|
|ConflictBetweenStreams|4|
|MissingMappings|5|

<h2 id="tocS_ResponseBody">ResponseBody</h2>

<a id="schemaresponsebody"></a>
<a id="schema_ResponseBody"></a>
<a id="tocSresponsebody"></a>
<a id="tocsresponsebody"></a>

```json
{
  "OperationId": "00000000-0000-0000-0000-000000000000",
  "Error": "Error message.",
  "Reason": "Reason that caused the error.",
  "Resolution": "Possible resolution for the error.",
  "Parameters": {
    "key1": "value1",
    "key2": "value2"
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|

