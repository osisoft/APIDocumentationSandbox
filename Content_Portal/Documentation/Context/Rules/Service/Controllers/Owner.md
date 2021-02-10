

<h1 id="context-rules-service-controllers-owner-owner">Owner</h1>

## Get Owner2

<a id="opIdOwner_Get Owner2"></a>

Gets the `Trustee` of the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/owner
```

<h3 id="owner_get-owner2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="owner_get-owner2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The `Trustee` of the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

## Set Owner2

<a id="opIdOwner_Set Owner2"></a>

Replaces the `Trustee` of the specified rule.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/owner
```

Sample request:

    PUT /sampleId/owner
    {
        "Type": 2,
        "TenantId": "tenantIdGuid",
        "ObjectId": "objectIdGuid"
    }

### Request Body

The owner.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

<h3 id="owner_set-owner2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="owner_set-owner2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The new `Trustee` of the specified rule.|
|400|[ResponseBody](#schemaresponsebody)|An invalid owner.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

## Get Owner

<a id="opIdOwner_Get Owner"></a>

Gets the `Trustee` of the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/owner
```

<h3 id="owner_get-owner-parameters">Parameters</h3>

`undefined routeOptions`<br/>The uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="owner_get-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The `Trustee` of the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

## Set Owner

<a id="opIdOwner_Set Owner"></a>

Replaces the `Trustee` of the specified rule.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/owner
```

Sample request:

    PUT /sampleId/owner
    {
        "Type": 2,
        "TenantId": "tenantIdGuid",
        "ObjectId": "objectIdGuid"
    }

### Request Body

The owner.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

<h3 id="owner_set-owner-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="owner_set-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The new `Trustee` of the specified rule.|
|400|[ResponseBody](#schemaresponsebody)|An invalid owner.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

# Schemas

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

|Name|Type|Required|Nullable|Description|
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

