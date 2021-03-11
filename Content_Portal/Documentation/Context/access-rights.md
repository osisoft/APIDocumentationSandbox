---
title: Context/access-rights v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="context-access-rights-access-rights">Access Rights</h1>

	

	

---
## List Access Rights

<a id="opIdAccessRights_List Access Rights"></a>

Gets a list of the `CommonAccessRights` the requesting `Identity` has on the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/accessrights
```

<h3 id="accessrights_list-access-rights-parameters">Parameters</h3>

`any routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string ruleId`<br/><br/>

<h3 id="accessrights_list-access-rights-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The `CommonAccessRights` the requesting `Identity` has on the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body
> 200 Response

```json
[
  "Read",
  "Write",
  "Delete",
  "ManageAccessControl"
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
## List Access Rights All

<a id="opIdAccessRights_List Access Rights All"></a>

Gets a list of the `CommonAccessRights` the requesting `Identity` has on the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/accessrights
```

<h3 id="accessrights_list-access-rights-all-parameters">Parameters</h3>

`any routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string ruleId`<br/><br/>

<h3 id="accessrights_list-access-rights-all-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The `CommonAccessRights` the requesting `Identity` has on the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body
> 200 Response

```json
[
  "Read",
  "Write",
  "Delete",
  "ManageAccessControl"
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

# Definitions

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

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|The id of a rule.|

