---
title: Integration/preview-data-queries v20210423.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Preview Data Queries
The Preview Data API allows users to [retrieve data](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html) for a specified data view.  This API is one portion of the [data views API](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/DataViewsAPIOverview/Data_Views_API_Overview.html).<br/>

## Get Data View Interpolated Data

<a id="opIdPreviewDataQueries_Get Data View Interpolated Data"></a>

Gets data for the provided data view and index parameters with paging. See [documentation on paging](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#paging) for further information.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/dataviews/data/interpolated
?startIndex={startIndex}&endIndex={endIndex}&interval={interval}&form={form}&countPerGroup={countPerGroup}&groupCount={groupCount}&count={count}&continuationToken={continuationToken}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string startIndex`
<br/>The requested start index, inclusive. The default value is the ```.DefaultStartIndex``` of the data view. Optional if a default value is specified
<br/><br/>`string endIndex`
<br/>The requested end index, inclusive. The default value is the ```.DefaultEndIndex``` of the data view. Optional if a default value is specified.
<br/><br/>`string interval`
<br/>The requested interval between index values. The default value is the ```.DefaultInterval``` of the data view. Optional if a default is specified.<br/><br/><br/>`string form`
<br/>The requested data [output format](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#format). Output formats: `default`, `table`, `tableh`, `csv`, `csvh`.
<br/><br/>`integer countPerGroup`
<br/>The number of rows per group. It overrides the endIndex.<br/><br/><br/>`integer groupCount`
<br/>The requested number of groups.<br/><br/><br/>`integer count`
<br/>The requested page size. The maximum is 250,000. If the parameter is not provided, [an optimal page size will be calculated](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#page-size).
<br/><br/>
`[optional] string continuationToken`
<br/>Used only when [paging](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#paging). Not specified when requesting the first page of data.
<br/><br/>

### Request Body

A `DataView` object to get the results for.<br/>

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
|200|string|Successfully retrieved data.<br/>|
|400|[ErrorResponse](#schemaerrorresponse)|The data view or the query parameters are not valid. See the response body for details.<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized for this operation<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Link|string|Hyperlinks to the first page and next page of data as applicable. Absence of the next link indicates that there is no additional data to be retrieved.<br/>|
|200|Next-Page|string|Hyperlink to the next page of results<br/>|
|200|First-Page|string|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
form=default
HTTP 200 OK
Content-Type: application/json
[
    {
        "Time": "2018-01-01T00:00:00Z",
        "Temperature": 24,
        "Flowrate": 44,
        "Volume": 245
    },
    {
        "Time": "2018-01-01T00:00:01Z",
        "Temperature": 24,
        "Flowrate": 44,
        "Volume": 245
    },
    {
        "Time": "2018-01-01T00:00:02Z",
        "Temperature": 24,
        "Flowrate": 44,
        "Volume": 245
    }
]
```
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
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---
# Definitions

## ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|
|ChildErrors|object|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}

```

---

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

