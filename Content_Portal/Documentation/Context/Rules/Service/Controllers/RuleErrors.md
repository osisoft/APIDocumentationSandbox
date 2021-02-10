

<h1 id="context-rules-service-controllers-ruleerrors-ruleerrors">RuleErrors</h1>

## Get Rule Errors By Rule Id

<a id="opIdRuleErrors_Get Rule Errors By Rule Id"></a>

Gets the `RuleErrorDto` objects for the specified ruleId.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/errors
```

<h3 id="ruleerrors_get-rule-errors-by-rule-id-parameters">Parameters</h3>

`string ruleId`<br/>The rule Id.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="ruleerrors_get-rule-errors-by-rule-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [RuleErrorDto](#schemaruleerrordto)s|An `IEnumerable`1`|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|

### Example response body

> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  }
}
```

## Delete Rule Errors By Rule Id

<a id="opIdRuleErrors_Delete Rule Errors By Rule Id"></a>

Deletes the `RuleErrorDto` objects associated with the specified rule.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/errors
```

<h3 id="ruleerrors_delete-rule-errors-by-rule-id-parameters">Parameters</h3>

`string ruleId`<br/>The rule Id.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="ruleerrors_delete-rule-errors-by-rule-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|

### Example response body

> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  }
}
```

# Schemas

<h2 id="tocS_RuleErrorDto">RuleErrorDto</h2>

<a id="schemaruleerrordto"></a>
<a id="schema_RuleErrorDto"></a>
<a id="tocSruleerrordto"></a>
<a id="tocsruleerrordto"></a>

```json
{
  "Id": "string",
  "RuleId": "string",
  "TimeGenerated": "2019-08-24T14:15:22Z",
  "ErrorDetails": "string",
  "ErrorMessageType": 0
}

```

### Properties

|Name|Type|Required|Nullable|Description|
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

<h2 id="tocS_ResponseBody">ResponseBody</h2>

<a id="schemaresponsebody"></a>
<a id="schema_ResponseBody"></a>
<a id="tocSresponsebody"></a>
<a id="tocsresponsebody"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|

