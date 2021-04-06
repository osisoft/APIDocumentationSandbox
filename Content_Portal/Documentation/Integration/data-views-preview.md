---
title: Integration/data-views-preview v20210405.11
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Data Views Preview

## Get Data Interpolated

<a id="opIdDataViewsPreview_Get Data Interpolated"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/data/interpolated
?startIndex={startIndex}&endIndex={endIndex}&interval={interval}&form={form}&countPerGroup={countPerGroup}&groupCount={groupCount}&count={count}&continuationToken={continuationToken}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string startIndex`
<br/><br/>`string endIndex`
<br/><br/>`string interval`
<br/><br/>`string form`
<br/><br/>`integer countPerGroup`
<br/><br/>`integer groupCount`
<br/><br/>`integer count`
<br/><br/>
`[optional] string continuationToken`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Available Field Sets

<a id="opIdDataViewsPreview_Get Available Field Sets"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/availablefieldsets
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Data Items

<a id="opIdDataViewsPreview_Get Data Items"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/dataitems/{queryId}
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string queryId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Field Mappings

<a id="opIdDataViewsPreview_Get Field Mappings"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/fieldmappings
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Groups

<a id="opIdDataViewsPreview_Get Groups"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/groups
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Ineligible Data Items

<a id="opIdDataViewsPreview_Get Ineligible Data Items"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/ineligibledataitems/{queryId}
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string queryId`
<br/><br/>
`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Statistics

<a id="opIdDataViewsPreview_Get Statistics"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/resolved/statistics
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
# Definitions

## DataView

<a id="schemadataview"></a>
<a id="schema_DataView"></a>
<a id="tocSdataview"></a>
<a id="tocsdataview"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|IndexField|[Field](#schemafield)|false|true|None|
|Queries|[[Query](#schemaquery)]|false|true|None|
|DataFieldSets|[[FieldSet](#schemafieldset)]|false|true|None|
|GroupingFields|[[Field](#schemafield)]|false|true|None|
|DefaultStartIndex|string|false|true|None|
|DefaultEndIndex|string|false|true|None|
|DefaultInterval|string|false|true|None|
|IndexTypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Shape|[DataViewShape](#schemadataviewshape)|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": 0,
          "Keys": [
            "string"
          ],
          "StreamReferenceNames": [
            "string"
          ],
          "Label": "string",
          "SummaryType": 0,
          "SummaryDirection": null,
          "IncludeUom": true
        }
      ],
      "IdentifyingField": {
        "Source": "[",
        "Keys": [
          null
        ],
        "StreamReferenceNames": [
          null
        ],
        "Label": "string",
        "SummaryType": "[",
        "SummaryDirection": null,
        "IncludeUom": true
      }
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}

```

---

## Field

<a id="schemafield"></a>
<a id="schema_Field"></a>
<a id="tocSfield"></a>
<a id="tocsfield"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Source|[FieldSource](#schemafieldsource)|false|false|None|
|Keys|string[]|false|true|None|
|StreamReferenceNames|string[]|false|true|None|
|Label|string|false|true|None|
|SummaryType|[SdsSummaryType](#schemasdssummarytype)|false|false|None|
|SummaryDirection|[SummaryDirection](#schemasummarydirection)|false|true|None|
|IncludeUom|boolean|false|false|None|

```json
{
  "Source": 0,
  "Keys": [
    "string"
  ],
  "StreamReferenceNames": [
    "string"
  ],
  "Label": "string",
  "SummaryType": 0,
  "SummaryDirection": 1,
  "IncludeUom": true
}

```

---

## FieldSource

<a id="schemafieldsource"></a>
<a id="schema_FieldSource"></a>
<a id="tocSfieldsource"></a>
<a id="tocsfieldsource"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|NotApplicable|0|
|Id|1|
|Name|2|
|PropertyId|3|
|PropertyName|4|
|Metadata|5|
|Tags|6|

---

## SdsSummaryType

<a id="schemasdssummarytype"></a>
<a id="schema_SdsSummaryType"></a>
<a id="tocSsdssummarytype"></a>
<a id="tocssdssummarytype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|None|0|
|Count|1|
|Minimum|2|
|Maximum|4|
|Range|8|
|Mean|16|
|StandardDeviation|32|
|PopulationStandardDeviation|64|
|Total|128|
|Skewness|256|
|Kurtosis|512|
|WeightedMean|1024|
|WeightedStandardDeviation|2048|
|WeightedPopulationStandardDeviation|4096|

---

## SummaryDirection

<a id="schemasummarydirection"></a>
<a id="schema_SummaryDirection"></a>
<a id="tocSsummarydirection"></a>
<a id="tocssummarydirection"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Forward|1|
|Backward|2|

---

## Query

<a id="schemaquery"></a>
<a id="schema_Query"></a>
<a id="tocSquery"></a>
<a id="tocsquery"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Kind|[DataItemResourceType](#schemadataitemresourcetype)|false|false|None|
|Value|string|false|true|None|

```json
{
  "Id": "string",
  "Kind": 1,
  "Value": "string"
}

```

---

## DataItemResourceType

<a id="schemadataitemresourcetype"></a>
<a id="schema_DataItemResourceType"></a>
<a id="tocSdataitemresourcetype"></a>
<a id="tocsdataitemresourcetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Stream|1|
|Asset|2|

---

## FieldSet

<a id="schemafieldset"></a>
<a id="schema_FieldSet"></a>
<a id="tocSfieldset"></a>
<a id="tocsfieldset"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|QueryId|string|false|true|None|
|DataFields|[[Field](#schemafield)]|false|true|None|
|IdentifyingField|[Field](#schemafield)|false|true|None|

```json
{
  "QueryId": "string",
  "DataFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "IdentifyingField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  }
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
|Empty|0|
|Object|1|
|Boolean|3|
|Char|4|
|SByte|5|
|Byte|6|
|Int16|7|
|UInt16|8|
|Int32|9|
|UInt32|10|
|Int64|11|
|UInt64|12|
|Single|13|
|Double|14|
|Decimal|15|
|DateTime|16|
|String|18|
|Guid|19|
|DateTimeOffset|20|
|TimeSpan|21|
|Version|22|
|NullableBoolean|103|
|NullableChar|104|
|NullableSByte|105|
|NullableByte|106|
|NullableInt16|107|
|NullableUInt16|108|
|NullableInt32|109|
|NullableUInt32|110|
|NullableInt64|111|
|NullableUInt64|112|
|NullableSingle|113|
|NullableDouble|114|
|NullableDecimal|115|
|NullableDateTime|116|
|NullableGuid|119|
|NullableDateTimeOffset|120|
|NullableTimeSpan|121|
|BooleanArray|203|
|CharArray|204|
|SByteArray|205|
|ByteArray|206|
|Int16Array|207|
|UInt16Array|208|
|Int32Array|209|
|UInt32Array|210|
|Int64Array|211|
|UInt64Array|212|
|SingleArray|213|
|DoubleArray|214|
|DecimalArray|215|
|DateTimeArray|216|
|StringArray|218|
|GuidArray|219|
|DateTimeOffsetArray|220|
|TimeSpanArray|221|
|VersionArray|222|
|Array|400|
|IList|401|
|IDictionary|402|
|IEnumerable|403|
|SdsType|501|
|SdsTypeProperty|502|
|SdsStreamView|503|
|SdsStreamViewProperty|504|
|SdsStreamViewMap|505|
|SdsStreamViewMapProperty|506|
|SdsStream|507|
|SdsStreamIndex|508|
|SdsTable|509|
|SdsColumn|510|
|SdsValues|511|
|SdsObject|512|
|SByteEnum|605|
|ByteEnum|606|
|Int16Enum|607|
|UInt16Enum|608|
|Int32Enum|609|
|UInt32Enum|610|
|Int64Enum|611|
|UInt64Enum|612|
|NullableSByteEnum|705|
|NullableByteEnum|706|
|NullableInt16Enum|707|
|NullableUInt16Enum|708|
|NullableInt32Enum|709|
|NullableUInt32Enum|710|
|NullableInt64Enum|711|
|NullableUInt64Enum|712|

---

## DataViewShape

<a id="schemadataviewshape"></a>
<a id="schema_DataViewShape"></a>
<a id="tocSdataviewshape"></a>
<a id="tocsdataviewshape"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Standard|0|
|Narrow|1|

---

