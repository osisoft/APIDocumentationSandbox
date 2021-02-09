

<h1 id="context-rules-service-controllers-accessrights-accessrights">AccessRights</h1>

## Get Access Rights

<a id="opIdAccessRights_Get Access Rights"></a>

Gets a list of the `CommonAccessRights` the requesting `Identity` has on the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/accessrights
```

<h3 id="accessrights_get-access-rights-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="accessrights_get-access-rights-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The `CommonAccessRights` the requesting `Identity` has on the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Get Access Rights All

<a id="opIdAccessRights_Get Access Rights All"></a>

Gets a list of the `CommonAccessRights` the requesting `Identity` has on the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/accessrights
```

<h3 id="accessrights_get-access-rights-all-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="accessrights_get-access-rights-all-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The `CommonAccessRights` the requesting `Identity` has on the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

<h2 id="tocS_RuleRouteOptions">RuleRouteOptions</h2>

<a id="schemarulerouteoptions"></a>
<a id="schema_RuleRouteOptions"></a>
<a id="tocSrulerouteoptions"></a>
<a id="tocsrulerouteoptions"></a>

```json
{
  "RuleId": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|The id of a rule.|

