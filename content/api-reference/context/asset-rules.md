---
uid: ""

---

# Asset Rules
Interacts with the IRuleStore and IAuthorizationService to process requests.

## `List Rules`

<a id="opIdAssetRules_List Rules"></a>

Gets all `AssetRuleModel` objects from the `IRuleStore` the requesting `!:Identity` has access to.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules
?Skip={Skip}&Count={Count}&KeepOldMetadata={KeepOldMetadata}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer Skip Skip`
<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count Count`
<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata KeepOldMetadata`
<br/>A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRuleModel](#schemaassetrulemodel)[]|The `AssetRuleModel` objects.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 200 Response

```json
[
  "{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"
]
```

> 400 Response

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

## `Create Rule With Server Generated Id`

<a id="opIdAssetRules_Create Rule With Server Generated Id"></a>

Creates a `RuleModel` object with a server generated `Id` in the `IRuleStore`.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The AssetRuleModel object to create.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "ExampleStreamId": "string",
  "AutomationId": "string",
  "Expressions": [
    {
      "Field": "string",
      "Specifications": [
        {
          "Type": null,
          "Value": null,
          "Name": null,
          "CharacterType": null,
          "CharacterLength": null,
          "RequiredDelimiters": null,
          "ValueMappings": null
        }
      ]
    }
  ],
  "Outputs": [
    {
      "Field": "string",
      "Value": null
    }
  ],
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[AssetRuleModel](#schemaassetrulemodel)|A link to the `AssetRuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the same id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 201 Response

```json
"{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"
```

> 400 Response

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

> 409 Response

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

## `Get Rule`

<a id="opIdAssetRules_Get Rule"></a>

Gets the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

#### Parameters

`any routeOptions`
<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string ruleId`
<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRuleModel](#schemaassetrulemodel)|The specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 200 Response

```json
"{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"
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

## `Create Rule`

<a id="opIdAssetRules_Create Rule"></a>

Gets or creates a `AssetRuleModel` object with the specified id in the `IRuleStore`.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

#### Parameters

`any routeOptions`
<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string ruleId`
<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The AssetRuleModel object.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "ExampleStreamId": "string",
  "AutomationId": "string",
  "Expressions": [
    {
      "Field": "string",
      "Specifications": [
        {
          "Type": null,
          "Value": null,
          "Name": null,
          "CharacterType": null,
          "CharacterLength": null,
          "RequiredDelimiters": null,
          "ValueMappings": null
        }
      ]
    }
  ],
  "Outputs": [
    {
      "Field": "string",
      "Value": null
    }
  ],
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[AssetRuleModel](#schemaassetrulemodel)|A link to the `AssetRuleModel` object.|
|302|None|An equivalent rule with the same id and definition already exists.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|None|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the specified id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 201 Response

```json
"{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"
```

> 400 Response

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

> 409 Response

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

## `Create Or Update Rule`

<a id="opIdAssetRules_Create Or Update Rule"></a>

Creates or updates the specified rule in the `IRuleStore`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
?Skip={Skip}&Count={Count}&KeepOldMetadata={KeepOldMetadata}
```

#### Parameters

`any routeOptions`
<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string ruleId`
<br/><br/>
`[optional] integer Skip Skip`
<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count Count`
<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata KeepOldMetadata`
<br/>A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The AssetRuleModel object to create or update.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "ExampleStreamId": "string",
  "AutomationId": "string",
  "Expressions": [
    {
      "Field": "string",
      "Specifications": [
        {
          "Type": null,
          "Value": null,
          "Name": null,
          "CharacterType": null,
          "CharacterLength": null,
          "RequiredDelimiters": null,
          "ValueMappings": null
        }
      ]
    }
  ],
  "Outputs": [
    {
      "Field": "string",
      "Value": null
    }
  ],
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRuleModel](#schemaassetrulemodel)|The updated `AssetRuleModel` object or a link to the new `AssetRuleModel` object.|
|201|[AssetRuleModel](#schemaassetrulemodel)|The updated `AssetRuleModel` object or a link to the new `AssetRuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 200 Response

```json
"{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"
```

> 400 Response

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

## `Delete Rule`

<a id="opIdAssetRules_Delete Rule"></a>

Deletes the specified rule from the `IRuleStore`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
?Skip={Skip}&Count={Count}&KeepOldMetadata={KeepOldMetadata}
```

#### Parameters

`any routeOptions`
<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string ruleId`
<br/><br/>
`[optional] integer Skip Skip`
<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count Count`
<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata KeepOldMetadata`
<br/>A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
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

## `Execute Rule`

<a id="opIdAssetRules_Execute Rule"></a>

Executes the specified rule.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/execute
```

#### Parameters

`any routeOptions`
<br/>The RuleRouteOptions uri route parameters.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string ruleId`
<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
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
## Definitions

### AssetRuleModel

<a id="schemaassetrulemodel"></a>
<a id="schema_AssetRuleModel"></a>
<a id="tocSassetrulemodel"></a>
<a id="tocsassetrulemodel"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|ExampleStreamId|string|false|true|None|
|AutomationId|string|false|true|None|
|Expressions|[[RuleExpression](#schemaruleexpression)]|false|true|None|
|Outputs|[[RuleOutput](#schemaruleoutput)]|false|true|None|
|CreationTime|date-time|false|false|None|
|ModifiedTime|date-time|false|false|None|

```json
"{\n    \"Id\": \"assetRuleId\",\n    \"Name\": \"name\",\n    \"Description\": \"description\",\n    \"ExampleStreamId\": \"exampleId\"\n    \"AutomationId\": \"00000000-0000-0000-0000-000000000000\",\n    \"Expressions\": [\n        {\n            \"Field\": \"Id\",\n            \"Specifications\": [\n                {\n                    \"Type\": \"Group\",\n                    \"Name\": \"id\"\n                }\n            ]\n        }\n    ],\n    \"Outputs\": [\n        {\n            \"Field\": \"asset\",\n            \"Value\": {\n                \"Id\" : \"assetId,\n                \"Name\": assetName,\n                \"Description\": description,\n                \"Metadata: [\n                    {\n                        \"Id\": \"metadataId\",\n                        \"Name\": \"name\",\n                        \"Description\": description,\n                        \"SdsTypeCode\": \"18\"\n                        \"key\": \"{id}\"\n                    }\n                ]\n                \"StreamReferences\": [\n                    {\n                        \"Id\": \"streamReferenceId\",\n                        \"Description\": \"description\",\n                        \"StreamId\": \"{id}\n                    }\n                ]\n            }\n        }\n    ],\n    \"CreationTime\": \"0001-01-01T00:00:00.0000000\",\n    \"ModifiedTime\": \"0001-01-01T00:00:00.0000000\"\n}"

```

---

### RuleExpression

<a id="schemaruleexpression"></a>
<a id="schema_RuleExpression"></a>
<a id="tocSruleexpression"></a>
<a id="tocsruleexpression"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Field|string|false|true|None|
|Specifications|[[Specification](#schemaspecification)]|false|true|None|

```json
{
  "Field": "string",
  "Specifications": [
    {
      "Type": "Unspecified",
      "Value": "string",
      "Name": "string",
      "CharacterType": "Any",
      "CharacterLength": 0,
      "RequiredDelimiters": [
        "string"
      ],
      "ValueMappings": {
        "property1": "string",
        "property2": "string"
      }
    }
  ]
}

```

---

### Specification

<a id="schemaspecification"></a>
<a id="schema_Specification"></a>
<a id="tocSspecification"></a>
<a id="tocsspecification"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[SpecificationType](#schemaspecificationtype)|false|false|None|
|Value|string|false|true|None|
|Name|string|false|true|None|
|CharacterType|[CharacterType](#schemacharactertype)|false|false|None|
|CharacterLength|int32|false|true|Null represents the longest string length within the group.|
|RequiredDelimiters|string[]|false|true|None|
|ValueMappings|object|false|true|None|

```json
{
  "Type": "Unspecified",
  "Value": "string",
  "Name": "string",
  "CharacterType": "Any",
  "CharacterLength": 0,
  "RequiredDelimiters": [
    "string"
  ],
  "ValueMappings": {
    "property1": "string",
    "property2": "string"
  }
}

```

---

### SpecificationType

<a id="schemaspecificationtype"></a>
<a id="schema_SpecificationType"></a>
<a id="tocSspecificationtype"></a>
<a id="tocsspecificationtype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Unspecified|Unspecified|
|Group|Group|
|Wildcard|Wildcard|
|Literal|Literal|
|Delimiter|Delimiter|

---

### CharacterType

<a id="schemacharactertype"></a>
<a id="schema_CharacterType"></a>
<a id="tocScharactertype"></a>
<a id="tocscharactertype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Any|Any|
|Letter|Letter|
|Digit|Digit|

---

### RuleOutput

<a id="schemaruleoutput"></a>
<a id="schema_RuleOutput"></a>
<a id="tocSruleoutput"></a>
<a id="tocsruleoutput"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Field|string|false|true|None|
|Value|any|false|true|None|

```json
{
  "Field": "string",
  "Value": null
}

```

---

### ResponseBody

<a id="schemaresponsebody"></a>
<a id="schema_ResponseBody"></a>
<a id="tocSresponsebody"></a>
<a id="tocsresponsebody"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|

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

### RuleRouteOptions

<a id="schemarulerouteoptions"></a>
<a id="schema_RuleRouteOptions"></a>
<a id="tocSrulerouteoptions"></a>
<a id="tocsrulerouteoptions"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|The id of a rule.|

```json
{
  "RuleId": "string"
}

```

---

### RuleModel

<a id="schemarulemodel"></a>
<a id="schema_RuleModel"></a>
<a id="tocSrulemodel"></a>
<a id="tocsrulemodel"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|ExampleStreamId|string|false|true|None|
|AutomationId|string|false|true|None|
|Expressions|[[RuleExpression](#schemaruleexpression)]|false|true|None|
|Outputs|[[RuleOutput](#schemaruleoutput)]|false|true|None|
|CreationTime|date-time|false|false|None|
|ModifiedTime|date-time|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "ExampleStreamId": "string",
  "AutomationId": "string",
  "Expressions": [
    {
      "Field": "string",
      "Specifications": [
        {
          "Type": "Unspecified",
          "Value": "string",
          "Name": "string",
          "CharacterType": "Any",
          "CharacterLength": 0,
          "RequiredDelimiters": [
            "string"
          ],
          "ValueMappings": {
            "property1": "string",
            "property2": "string"
          }
        }
      ]
    }
  ],
  "Outputs": [
    {
      "Field": "string",
      "Value": null
    }
  ],
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}

```

---

