---
title: AssetRuleService/asset-change-data v20210331.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Asset Change Data

## List Change Data For Asset

<a id="opIdAssetChangeData_List Change Data For Asset"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/asset/{assetId}
```

#### Parameters

`string assetId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetChangeData](#schemaassetchangedata)[]|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

#### Example response body
> 200 Response

```json
[
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
  },
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
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

## List Change Data For Rule

<a id="opIdAssetChangeData_List Change Data For Rule"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/rule/{ruleId}
?Skip={Skip}&Count={Count}
```

#### Parameters

`string ruleId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer Skip`
<br/>An Int32 specifying the number of results to skip.
Defaults to 0.<br/><br/>`[optional] integer Count`
<br/>An Int32 specifying the number of results to return.
Defaults to 100.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetChangeData](#schemaassetchangedata)[]|None|
|400|[ResponseBody](#schemaresponsebody)|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

#### Example response body
> 200 Response

```json
[
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
  },
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
  }
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

## Get Statistics For Rule

<a id="opIdAssetChangeData_Get Statistics For Rule"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/rule/{ruleId}/statistics
```

#### Parameters

`string ruleId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRuleStatistics](#schemaassetrulestatistics)|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

#### Example response body
> 200 Response

```json
{
  "AssetsAffected": 0,
  "StreamsExecutedOn": 0
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

## List Change Data For Stream

<a id="opIdAssetChangeData_List Change Data For Stream"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/admin/assetrules/changedata/stream/{streamId}
```

#### Parameters

`string streamId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetChangeData](#schemaassetchangedata)[]|None|
|403|[ResponseBody](#schemaresponsebody)|None|
|500|[ResponseBody](#schemaresponsebody)|None|

#### Example response body
> 200 Response

```json
[
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
  },
  {
    "RuleId": "ruleId",
    "StreamId": "streamId",
    "GeneratedAsset": {
      "Id": "id",
      "AssetTypeId": "assetTypeId",
      "Name": "name",
      "Description": "description",
      "Metadata": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "SdsTypeCode": 18,
          "Value": "value",
          "Uom": "uom"
        }
      ],
      "StreamReferences": [
        {
          "Id": "id",
          "Name": "name",
          "Description": "description",
          "StreamId": "streamId"
        }
      ],
      "Status": {
        "Name": "name",
        "Description": "description",
        "StreamReferenceId": "streamReferenceId",
        "StreamPropertyId": "streamPropertyId",
        "ValueStatusMappings": [
          {
            "Value": "value",
            "Status": 1,
            "DisplayName": "displayName"
          }
        ]
      }
    }
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
# Definitions

## AssetRuleStatistics

<a id="schemaassetrulestatistics"></a>
<a id="schema_AssetRuleStatistics"></a>
<a id="tocSassetrulestatistics"></a>
<a id="tocsassetrulestatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|AssetsAffected|int32|false|false|None|
|StreamsExecutedOn|int32|false|false|None|

```json
{
  "AssetsAffected": 0,
  "StreamsExecutedOn": 0
}

```

---

## ResponseBody

<a id="schemaresponsebody"></a>
<a id="schema_ResponseBody"></a>
<a id="tocSresponsebody"></a>
<a id="tocsresponsebody"></a>

### Properties

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

## AssetChangeData

<a id="schemaassetchangedata"></a>
<a id="schema_AssetChangeData"></a>
<a id="tocSassetchangedata"></a>
<a id="tocsassetchangedata"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|None|
|StreamId|string|false|true|None|
|GeneratedAsset|[AssetDto](#schemaassetdto)|false|true|The asset which was generated by the RuleId and StreamId combination.|

```json
{
  "RuleId": "ruleId",
  "StreamId": "streamId",
  "GeneratedAsset": {
    "Id": "id",
    "AssetTypeId": "assetTypeId",
    "Name": "name",
    "Description": "description",
    "Metadata": [
      {
        "Id": "id",
        "Name": "name",
        "Description": "description",
        "SdsTypeCode": 18,
        "Value": "value",
        "Uom": "uom"
      }
    ],
    "StreamReferences": [
      {
        "Id": "id",
        "Name": "name",
        "Description": "description",
        "StreamId": "streamId"
      }
    ],
    "Status": {
      "Name": "name",
      "Description": "description",
      "StreamReferenceId": "streamReferenceId",
      "StreamPropertyId": "streamPropertyId",
      "ValueStatusMappings": [
        {
          "Value": "value",
          "Status": 1,
          "DisplayName": "displayName"
        }
      ]
    }
  }
}

```

---

## AssetDto

<a id="schemaassetdto"></a>
<a id="schema_AssetDto"></a>
<a id="tocSassetdto"></a>
<a id="tocsassetdto"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|AssetTypeId|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|Metadata|[[MetadataDto](#schemametadatadto)]|false|true|None|
|StreamReferences|[[StreamReferenceDto](#schemastreamreferencedto)]|false|true|None|
|Status|[StatusMappingDto](#schemastatusmappingdto)|false|true|None|

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

---

## MetadataDto

<a id="schemametadatadto"></a>
<a id="schema_MetadataDto"></a>
<a id="tocSmetadatadto"></a>
<a id="tocsmetadatadto"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|SdsTypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Value|any|false|true|None|
|Uom|string|false|true|None|

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

---

## SdsTypeCode

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

---

## StreamReferenceDto

<a id="schemastreamreferencedto"></a>
<a id="schema_StreamReferenceDto"></a>
<a id="tocSstreamreferencedto"></a>
<a id="tocsstreamreferencedto"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|StreamId|string|true|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "StreamId": "string"
}

```

---

## StatusMappingDto

<a id="schemastatusmappingdto"></a>
<a id="schema_StatusMappingDto"></a>
<a id="tocSstatusmappingdto"></a>
<a id="tocsstatusmappingdto"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamReferenceId|string|true|false|None|
|StreamPropertyId|string|true|false|None|
|ValueStatusMappings|[[ValueStatusMappingDto](#schemavaluestatusmappingdto)]|false|true|None|

```json
{
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

---

## ValueStatusMappingDto

<a id="schemavaluestatusmappingdto"></a>
<a id="schema_ValueStatusMappingDto"></a>
<a id="tocSvaluestatusmappingdto"></a>
<a id="tocsvaluestatusmappingdto"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|any|false|true|None|
|Status|[StatusEnum](#schemastatusenum)|true|false|None|
|DisplayName|string|false|true|None|

```json
{
  "Value": null,
  "Status": 0,
  "DisplayName": "string"
}

```

---

## StatusEnum

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

---

