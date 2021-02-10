

<h1 id="context-rules-service-controllers-admin-admin">Admin</h1>

## Get Statistics2

<a id="opIdAdmin_Get Statistics2"></a>

Gets the `StoreStatistics` on the `IRuleStore` .

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/statistics
```

<h3 id="admin_get-statistics2-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="admin_get-statistics2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[StoreStatistics](#schemastorestatistics)|The `IRuleStore` `StoreStatistics` .|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RuleCount": 0
}
```

## Get Statistics

<a id="opIdAdmin_Get Statistics"></a>

Gets the `StoreStatistics` on the `IRuleStore` .

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/metadatarules/statistics
```

<h3 id="admin_get-statistics-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="admin_get-statistics-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[StoreStatistics](#schemastorestatistics)|The `IRuleStore` `StoreStatistics` .|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RuleCount": 0
}
```

# Schemas

<h2 id="tocS_StoreStatistics">StoreStatistics</h2>

<a id="schemastorestatistics"></a>
<a id="schema_StoreStatistics"></a>
<a id="tocSstorestatistics"></a>
<a id="tocsstorestatistics"></a>

```json
{
  "RuleCount": 0
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleCount|int32|false|false|None|

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

