

<h1 id="assetruleservice-controller-assetchangedata-assetchangedata">AssetChangeData</h1>

## Get Change Data For Asset

<a id="opIdAssetChangeData_Get Change Data For Asset"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/asset/{assetId}
```

<h3 id="assetchangedata_get-change-data-for-asset-parameters">Parameters</h3>

`string assetId`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="assetchangedata_get-change-data-for-asset-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AssetChangeData](#schemaassetchangedata)s|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

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

## Get Change Data For Rule

<a id="opIdAssetChangeData_Get Change Data For Rule"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/rule/{ruleId}
```

<h3 id="assetchangedata_get-change-data-for-rule-parameters">Parameters</h3>

`string ruleId`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>undefined<br/><br/>`[optional] integer Count`<br/>undefined<br/><br/>

<h3 id="assetchangedata_get-change-data-for-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AssetChangeData](#schemaassetchangedata)s|None|
|400|[ResponseBody](#schemaresponsebody)|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

### Example response body

> 400 Response

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

## Get Statistics For Rule

<a id="opIdAssetChangeData_Get Statistics For Rule"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/rule/{ruleId}/statistics
```

<h3 id="assetchangedata_get-statistics-for-rule-parameters">Parameters</h3>

`string ruleId`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="assetchangedata_get-statistics-for-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRuleStatistics](#schemaassetrulestatistics)|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

### Example response body

> 200 Response

```json
{
  "AssetsAffected": 0,
  "StreamsExecutedOn": 0
}
```

## Get Change Data For Stream

<a id="opIdAssetChangeData_Get Change Data For Stream"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/stream/{streamId}
```

<h3 id="assetchangedata_get-change-data-for-stream-parameters">Parameters</h3>

`string streamId`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="assetchangedata_get-change-data-for-stream-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AssetChangeData](#schemaassetchangedata)s|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

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

<h2 id="tocS_AssetRuleStatistics">AssetRuleStatistics</h2>

<a id="schemaassetrulestatistics"></a>
<a id="schema_AssetRuleStatistics"></a>
<a id="tocSassetrulestatistics"></a>
<a id="tocsassetrulestatistics"></a>

```json
{
  "AssetsAffected": 0,
  "StreamsExecutedOn": 0
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|AssetsAffected|int32|false|false|None|
|StreamsExecutedOn|int32|false|false|None|

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

<h2 id="tocS_AssetChangeData">AssetChangeData</h2>

<a id="schemaassetchangedata"></a>
<a id="schema_AssetChangeData"></a>
<a id="tocSassetchangedata"></a>
<a id="tocsassetchangedata"></a>

```json
{
  "RuleId": "string",
  "StreamId": "string",
  "GeneratedAsset": {
    "Id": "string",
    "AssetTypeId": "string",
    "Name": "string",
    "Description": "string",
    "Metadata": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "SdsTypeCode": "[",
        "Value": null,
        "Uom": "string"
      }
    ],
    "StreamReferences": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "StreamId": "string"
      }
    ],
    "Status": {
      "Name": null,
      "Description": null,
      "StreamReferenceId": null,
      "StreamPropertyId": null,
      "ValueStatusMappings": null
    }
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|None|
|StreamId|string|false|true|None|
|GeneratedAsset|[AssetDto](#schemaassetdto)|false|true|The asset which was generated by the RuleId and StreamId combination.|

<h2 id="tocS_AssetDto">AssetDto</h2>

<a id="schemaassetdto"></a>
<a id="schema_AssetDto"></a>
<a id="tocSassetdto"></a>
<a id="tocsassetdto"></a>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "Name": "string",
    "Description": "string",
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {
        "Value": null,
        "Status": "[",
        "DisplayName": "string"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|AssetTypeId|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|Metadata|[[MetadataDto](#schemametadatadto)]|false|true|None|
|StreamReferences|[[StreamReferenceDto](#schemastreamreferencedto)]|false|true|None|
|Status|[StatusMappingDto](#schemastatusmappingdto)|false|true|None|

<h2 id="tocS_MetadataDto">MetadataDto</h2>

<a id="schemametadatadto"></a>
<a id="schema_MetadataDto"></a>
<a id="tocSmetadatadto"></a>
<a id="tocsmetadatadto"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "SdsTypeCode": "Empty",
  "Value": null,
  "Uom": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|SdsTypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Value|any|false|true|None|
|Uom|string|false|true|None|

<h2 id="tocS_SdsTypeCode">SdsTypeCode</h2>

<a id="schemasdstypecode"></a>
<a id="schema_SdsTypeCode"></a>
<a id="tocSsdstypecode"></a>
<a id="tocssdstypecode"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Empty|Empty|
|Object|Object|
|Boolean|Boolean|
|Char|Char|
|SByte|SByte|
|Byte|Byte|
|Int16|Int16|
|UInt16|UInt16|
|Int32|Int32|
|UInt32|UInt32|
|Int64|Int64|
|UInt64|UInt64|
|Single|Single|
|Double|Double|
|Decimal|Decimal|
|DateTime|DateTime|
|String|String|
|Guid|Guid|
|DateTimeOffset|DateTimeOffset|
|TimeSpan|TimeSpan|
|Version|Version|
|NullableBoolean|NullableBoolean|
|NullableChar|NullableChar|
|NullableSByte|NullableSByte|
|NullableByte|NullableByte|
|NullableInt16|NullableInt16|
|NullableUInt16|NullableUInt16|
|NullableInt32|NullableInt32|
|NullableUInt32|NullableUInt32|
|NullableInt64|NullableInt64|
|NullableUInt64|NullableUInt64|
|NullableSingle|NullableSingle|
|NullableDouble|NullableDouble|
|NullableDecimal|NullableDecimal|
|NullableDateTime|NullableDateTime|
|NullableGuid|NullableGuid|
|NullableDateTimeOffset|NullableDateTimeOffset|
|NullableTimeSpan|NullableTimeSpan|
|BooleanArray|BooleanArray|
|CharArray|CharArray|
|SByteArray|SByteArray|
|ByteArray|ByteArray|
|Int16Array|Int16Array|
|UInt16Array|UInt16Array|
|Int32Array|Int32Array|
|UInt32Array|UInt32Array|
|Int64Array|Int64Array|
|UInt64Array|UInt64Array|
|SingleArray|SingleArray|
|DoubleArray|DoubleArray|
|DecimalArray|DecimalArray|
|DateTimeArray|DateTimeArray|
|StringArray|StringArray|
|GuidArray|GuidArray|
|DateTimeOffsetArray|DateTimeOffsetArray|
|TimeSpanArray|TimeSpanArray|
|VersionArray|VersionArray|
|Array|Array|
|IList|IList|
|IDictionary|IDictionary|
|IEnumerable|IEnumerable|
|SdsType|SdsType|
|SdsTypeProperty|SdsTypeProperty|
|SdsStreamView|SdsStreamView|
|SdsStreamViewProperty|SdsStreamViewProperty|
|SdsStreamViewMap|SdsStreamViewMap|
|SdsStreamViewMapProperty|SdsStreamViewMapProperty|
|SdsStream|SdsStream|
|SdsStreamIndex|SdsStreamIndex|
|SdsTable|SdsTable|
|SdsColumn|SdsColumn|
|SdsValues|SdsValues|
|SdsObject|SdsObject|
|SByteEnum|SByteEnum|
|ByteEnum|ByteEnum|
|Int16Enum|Int16Enum|
|UInt16Enum|UInt16Enum|
|Int32Enum|Int32Enum|
|UInt32Enum|UInt32Enum|
|Int64Enum|Int64Enum|
|UInt64Enum|UInt64Enum|
|NullableSByteEnum|NullableSByteEnum|
|NullableByteEnum|NullableByteEnum|
|NullableInt16Enum|NullableInt16Enum|
|NullableUInt16Enum|NullableUInt16Enum|
|NullableInt32Enum|NullableInt32Enum|
|NullableUInt32Enum|NullableUInt32Enum|
|NullableInt64Enum|NullableInt64Enum|
|NullableUInt64Enum|NullableUInt64Enum|

<h2 id="tocS_StreamReferenceDto">StreamReferenceDto</h2>

<a id="schemastreamreferencedto"></a>
<a id="schema_StreamReferenceDto"></a>
<a id="tocSstreamreferencedto"></a>
<a id="tocsstreamreferencedto"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "StreamId": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|StreamId|string|true|false|None|

<h2 id="tocS_StatusMappingDto">StatusMappingDto</h2>

<a id="schemastatusmappingdto"></a>
<a id="schema_StatusMappingDto"></a>
<a id="tocSstatusmappingdto"></a>
<a id="tocsstatusmappingdto"></a>

```json
{
  "Name": "string",
  "Description": "string",
  "StreamReferenceId": "string",
  "StreamPropertyId": "string",
  "ValueStatusMappings": [
    {
      "Value": null,
      "Status": 0,
      "DisplayName": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|true|false|None|
|Description|string|false|true|None|
|StreamReferenceId|string|true|false|None|
|StreamPropertyId|string|true|false|None|
|ValueStatusMappings|[[ValueStatusMappingDto](#schemavaluestatusmappingdto)]|false|true|None|

<h2 id="tocS_ValueStatusMappingDto">ValueStatusMappingDto</h2>

<a id="schemavaluestatusmappingdto"></a>
<a id="schema_ValueStatusMappingDto"></a>
<a id="tocSvaluestatusmappingdto"></a>
<a id="tocsvaluestatusmappingdto"></a>

```json
{
  "Value": null,
  "Status": 0,
  "DisplayName": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|any|false|true|None|
|Status|[StatusEnum](#schemastatusenum)|true|false|None|
|DisplayName|string|false|true|None|

<h2 id="tocS_StatusEnum">StatusEnum</h2>

<a id="schemastatusenum"></a>
<a id="schema_StatusEnum"></a>
<a id="tocSstatusenum"></a>
<a id="tocsstatusenum"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Unknown|0|
|Good|1|
|Warning|2|
|Bad|3|

