---
title: context/asset-rule-preview v20210428.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Asset Rule Preview

## `Get Preview Results`

<a id="opIdAssetRulePreview_Get Preview Results"></a>

Gets a `AssetRulePreviewResult`.

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/preview/assetrules
?token={token}&skip={skip}&count={count}
```

#### Parameters

`string token`
<br/>A Guid which corresponds to a preview that has been created using the CancellationToken) method.<br/><br/>`integer skip`
<br/>An Int32 to determine the number of preview results to skip.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer count`
<br/>An Int32 to determine the number of preview results to return.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AssetRulePreviewResult](#schemaassetrulepreviewresult)|A `AssetRulePreviewResult` object.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified preview was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 200 Response

```json
{
  "Status": "status",
  "Assets": [
    {
      "AssetId": "assetId",
      "ChangeType": "changeType",
      "Asset": {
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
  ],
  "Statistics": {
    "Streams": 1,
    "TotalResults": 1
  }
}
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

## `Start Preview`

<a id="opIdAssetRulePreview_Start Preview"></a>

Creates a `RulePreviewResponse` of a `RuleModel` object.

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/preview/assetrules
?KeepOldMetadata={KeepOldMetadata}&Skip={Skip}&Count={Count}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] boolean KeepOldMetadata`
<br/><br/>`[optional] integer Skip`
<br/><br/>`[optional] integer Count`
<br/><br/>

### Request Body

The RuleModel object to preview.<br/>

```json
{
  "Id": "ruleId",
  "Name": "name",
  "Description": "description",
  "AutomationId": "00000000-0000-0000-0000-000000000000",
  "Expressions": [
    {
      "Field": "Id",
      "Pattern": "{id}"
    }
  ],
  "Outputs": [
    {
      "Field": "Metadata",
      "Value": {
        "key": "{id}"
      }
    }
  ],
  "CreationTime": "0001-01-01T00:00:00",
  "ModifiedTime": "0001-01-01T00:00:00"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|202|[RulePreviewResponse](#schemarulepreviewresponse)|A `RulePreviewResponse` object.|
|204|[ResponseBody](#schemaresponsebody)|A `RulePreviewResponse` object.|
|400|[ResponseBody](#schemaresponsebody)|Invalid rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|
|503|[ResponseBody](#schemaresponsebody)|Dependent service error.|

#### Example response body
> 202 Response

```json
{
  "PreviewLink": "/api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/preview/assetrules?Token=00000000-0000-0000-0000-000000000000",
  "Expires": 7200
}
```

> 204 Response

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

> 503 Response

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

## `Cancel Preview`

<a id="opIdAssetRulePreview_Cancel Preview"></a>

Cancels a running preview.

### Request
```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/preview/assetrules
?token={token}
```

#### Parameters

`string token`
<br/>A Guid which corresponds to a preview that has been created using the CancellationToken) method.<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified preview was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
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

### RulePreviewResponse

<a id="schemarulepreviewresponse"></a>
<a id="schema_RulePreviewResponse"></a>
<a id="tocSrulepreviewresponse"></a>
<a id="tocsrulepreviewresponse"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PreviewLink|string|false|true|None|
|Expires|int32|false|false|None|

```json
{
  "PreviewLink": "string",
  "Expires": 0
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
|AutomationId|string|false|true|None|
|Expressions|[[RuleExpression](#schemaruleexpression)]|false|true|None|
|Outputs|[[RuleOutput](#schemaruleoutput)]|false|true|None|
|CreationTime|date-time|false|false|None|
|ModifiedTime|date-time|false|false|None|

```json
{
  "Id": "ruleId",
  "Name": "name",
  "Description": "description",
  "AutomationId": "00000000-0000-0000-0000-000000000000",
  "Expressions": [
    {
      "Field": "Id",
      "Pattern": "{id}"
    }
  ],
  "Outputs": [
    {
      "Field": "Metadata",
      "Value": {
        "key": "{id}"
      }
    }
  ],
  "CreationTime": "0001-01-01T00:00:00",
  "ModifiedTime": "0001-01-01T00:00:00"
}

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

### AssetRulePreviewResult

<a id="schemaassetrulepreviewresult"></a>
<a id="schema_AssetRulePreviewResult"></a>
<a id="tocSassetrulepreviewresult"></a>
<a id="tocsassetrulepreviewresult"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Status|string|false|true|None|
|Assets|[[AssetPreviewData](#schemaassetpreviewdata)]|false|true|None|
|Statistics|[AssetRulePreviewStatistics](#schemaassetrulepreviewstatistics)|false|true|None|

```json
{
  "Status": "status",
  "Assets": [
    {
      "AssetId": "assetId",
      "ChangeType": "changeType",
      "Asset": {
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
  ],
  "Statistics": {
    "Streams": 1,
    "TotalResults": 1
  }
}

```

---

### AssetPreviewData

<a id="schemaassetpreviewdata"></a>
<a id="schema_AssetPreviewData"></a>
<a id="tocSassetpreviewdata"></a>
<a id="tocsassetpreviewdata"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|AssetId|string|false|true|None|
|Asset|[AssetDto](#schemaassetdto)|false|true|None|

```json
{
  "AssetId": "string",
  "Asset": {
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
      "StreamReferenceId": null,
      "StreamPropertyId": null,
      "ValueStatusMappings": null
    }
  }
}

```

---

### AssetDto

<a id="schemaassetdto"></a>
<a id="schema_AssetDto"></a>
<a id="tocSassetdto"></a>
<a id="tocsassetdto"></a>

#### Properties

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

### MetadataDto

<a id="schemametadatadto"></a>
<a id="schema_MetadataDto"></a>
<a id="tocSmetadatadto"></a>
<a id="tocsmetadatadto"></a>

#### Properties

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

### SdsTypeCode

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

### StreamReferenceDto

<a id="schemastreamreferencedto"></a>
<a id="schema_StreamReferenceDto"></a>
<a id="tocSstreamreferencedto"></a>
<a id="tocsstreamreferencedto"></a>

#### Properties

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

### StatusMappingDto

<a id="schemastatusmappingdto"></a>
<a id="schema_StatusMappingDto"></a>
<a id="tocSstatusmappingdto"></a>
<a id="tocsstatusmappingdto"></a>

#### Properties

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

### ValueStatusMappingDto

<a id="schemavaluestatusmappingdto"></a>
<a id="schema_ValueStatusMappingDto"></a>
<a id="tocSvaluestatusmappingdto"></a>
<a id="tocsvaluestatusmappingdto"></a>

#### Properties

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

### StatusEnum

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

### AssetRulePreviewStatistics

<a id="schemaassetrulepreviewstatistics"></a>
<a id="schema_AssetRulePreviewStatistics"></a>
<a id="tocSassetrulepreviewstatistics"></a>
<a id="tocsassetrulepreviewstatistics"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamsProcessed|int32|false|false|Streams used in the preview.|
|TotalResults|int32|false|false|Total number of asset results.|
|ExecutionErrors|int32|false|false|Number of errors generted during execution|

```json
{
  "StreamsProcessed": 0,
  "TotalResults": 0,
  "ExecutionErrors": 0
}

```

---

