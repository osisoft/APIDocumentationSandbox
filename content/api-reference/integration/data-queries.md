---
title: integration/data-queries v20210426.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Data Queries
The Data API allows users to [retrieve data](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html) for a specified data view.  This API is one portion of the [data views API](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/DataViewsAPIOverview/Data_Views_API_Overview.html).

## Get Data View Interpolated Data

<a id="opIdDataQueries_Get Data View Interpolated Data"></a>

Gets data for the provided index parameters with paging. See [documentation on paging](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#paging) for further information.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/data/interpolated
?startIndex={startIndex}&endIndex={endIndex}&interval={interval}&form={form}&continuationToken={continuationToken}&count={count}&cache={cache}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>`string startIndex`
<br/>The requested start index, inclusive. The default value is the ```.DefaultStartIndex``` of the data view. Optional if a default value is specified
<br/><br/>`string endIndex`
<br/>The requested end index, inclusive. The default value is the ```.DefaultEndIndex``` of the data view. Optional if a default value is specified.
<br/><br/>`string interval`
<br/>The requested interval between index values. The default value is the ```.DefaultInterval``` of the data view. Optional if a default is specified.<br/><br/><br/>`string form`
<br/>The requested data [output format](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#format). Output formats: `default`, `table`, `tableh`, `csv`, `csvh`.
<br/><br/>`string continuationToken`
<br/>Used only when [paging](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#paging). Not specified when requesting the first page of data.
<br/><br/>`integer count`
<br/>The requested page size. The maximum is 250,000. If the parameter is not provided, [an optimal page size will be calculated](https://ocs-docs.osisoft.com/Content_Portal/Documentation/DataViews/GetDataViewData/Quick_Start_Get_Data_View_Data.html#page-size).
<br/><br/>
`[optional] string cache`
<br/>Controls when the data view backing resources are to be refreshed. Used only when requesting the first page of data. Ignored if used with the continuationToken. Values are:

| Value | Description | 
|--|--|
| `Refresh` | Force the resource to re-resolve.  This is the default value for this API route.  
| `Preserve`| Use cached information, if available.
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|Successfully retrieved data.<br/>|
|400|[ErrorResponse](#schemaerrorresponse)|The request could not be understood by the server due to malformed syntax.<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized for this operation<br/>|
|404|[ErrorResponse](#schemaerrorresponse)|The specified data view identifier is not found<br/>|
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

```csv
form=csv
HTTP 200 OK
Content-Type: text/csv
2018-01-01T00:00:00Z,24,44,245
2018-01-01T00:00:01Z,24,44,245
2018-01-01T00:00:02Z,24,44,245
```

```csv
form=csvh
HTTP 200 OK
Content-Type: text/csv
Time,Temperature,Flowrate,Volume
2018-01-01T00:00:00Z,24,44,245
2018-01-01T00:00:01Z,24,44,245
2018-01-01T00:00:02Z,24,44,245
```

```json
form=table
HTTP 200 OK
Content-Type: application/json
{
   "Columns": [
      {
          "Name": "Time",
          "Type": "DateTime"
      },
      {
          "Name": "Temperature",
          "Type": "Int32"
      },
      {
          "Name": "Flowrate",
          "Type": "Int32"
      },
      {
          "Name": "Volume",
          "Type": "Int32"
      }
  ],
  "Rows": [
    [
      "2018-01-01T00:00:00Z",
      24,
      44,
      245
    ],
    [
      "2018-01-01T00:00:01Z",
      24,
      44,
      245
    ],
    [
      "2018-01-01T00:00:02Z",
      24,
      44,
      245
    ]
  ]
}
```

```json
form=tableh
HTTP 200 OK
Content-Type: application/json
{
  "Columns": [
      {
          "Name": "Time",
          "Type": "DateTime"
      },
      {
          "Name": "Temperature",
          "Type": "Int32"
      },
      {
          "Name": "Flowrate",
          "Type": "Int32"
      },
      {
          "Name": "Volume",
          "Type": "Int32"
      }
  ],
  "Rows": [
      [
          "Time",
          "Temperature",
          "Flowrate",
          "Volume"
      ],
      [
          "2018-01-01T00:00:00Z",
          24,
          44,
          245
      ],
      [
          "2018-01-01T00:00:01Z",
          24,
          44,
          245
      ],
      [
          "2018-01-01T00:00:02Z",
          24,
          44,
          245
      ]
   ]
}
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

