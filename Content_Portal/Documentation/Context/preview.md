---
title: Context/preview v20210304.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="context-preview-preview">Preview</h1>

	

	

	

	

	

	

	

	

	

	

---
## Get Preview

<a id="opIdPreview_Get Preview"></a>

Creates a `RulePreviewResult` of a metadata `RuleModel` object.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/preview/metadatarules
```

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
  "ValueMappings": {
    "{id}": {
      "key": "value"
    }
  },
  "CreationTime": "0001-01-01T00:00:00",
  "ModifiedTime": "0001-01-01T00:00:00"
}
```

<h3 id="preview_get-preview-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] integer Skip`<br/>An Int32 specifying the number of results to skip.<br/><br/>`[optional] integer Count`<br/>An Int32 specifying the number of results to return.<br/><br/>

#### Detailed descriptions

**Skip**: An Int32 specifying the number of results to skip.
Defaults to 0.

**Count**: An Int32 specifying the number of results to return.
Defaults to 100.

<h3 id="preview_get-preview-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RulePreviewResult](#schemarulepreviewresult)|A `RulePreviewResult` object.|
|400|[ResponseBody](#schemaresponsebody)|Invalid rule or query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|
|503|[ResponseBody](#schemaresponsebody)|Dependent service error.|

### Example response body
> 200 Response

```json
{
  "Results": [
    {
      "Name": "name",
      "Id": "id",
      "Description": "description",
      "Metadata": {
        "key": "value"
      }
    }
  ],
  "Statistics": {
    "StreamsAffected": 1,
    "NewMetadataKeys": 1,
    "NewMetadataValues": 1,
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

# Definitions

<h2 id="tocS_RulePreviewResult">RulePreviewResult</h2>

<a id="schemarulepreviewresult"></a>
<a id="schema_RulePreviewResult"></a>
<a id="tocSrulepreviewresult"></a>
<a id="tocsrulepreviewresult"></a>

```json
{
  "Results": [
    {
      "Name": "name",
      "Id": "id",
      "Description": "description",
      "Metadata": {
        "key": "value"
      }
    }
  ],
  "Statistics": {
    "StreamsAffected": 1,
    "NewMetadataKeys": 1,
    "NewMetadataValues": 1,
    "TotalResults": 1
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|[[StreamPreviewData](#schemastreampreviewdata)]|false|true|None|
|Statistics|[RulePreviewStatistics](#schemarulepreviewstatistics)|false|true|None|

<h2 id="tocS_StreamPreviewData">StreamPreviewData</h2>

<a id="schemastreampreviewdata"></a>
<a id="schema_StreamPreviewData"></a>
<a id="tocSstreampreviewdata"></a>
<a id="tocsstreampreviewdata"></a>

```json
{
  "Name": "string",
  "Id": "string",
  "Description": "string",
  "Metadata": {
    "property1": "string",
    "property2": "string"
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|None|
|Id|string|false|true|None|
|Description|string|false|true|None|
|Metadata|object|false|true|None|

<h2 id="tocS_RulePreviewStatistics">RulePreviewStatistics</h2>

<a id="schemarulepreviewstatistics"></a>
<a id="schema_RulePreviewStatistics"></a>
<a id="tocSrulepreviewstatistics"></a>
<a id="tocsrulepreviewstatistics"></a>

```json
{
  "StreamsAffected": 0,
  "NewMetadataKeys": 0,
  "NewMetadataValues": 0,
  "TotalResults": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamsAffected|int32|false|false|None|
|NewMetadataKeys|int32|false|false|None|
|NewMetadataValues|int32|false|false|None|
|TotalResults|int32|false|false|None|

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

<h2 id="tocS_RuleModel">RuleModel</h2>

<a id="schemarulemodel"></a>
<a id="schema_RuleModel"></a>
<a id="tocSrulemodel"></a>
<a id="tocsrulemodel"></a>

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
  "ValueMappings": {
    "{id}": {
      "key": "value"
    }
  },
  "CreationTime": "0001-01-01T00:00:00",
  "ModifiedTime": "0001-01-01T00:00:00"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|AutomationId|string|false|true|None|
|Expressions|[[RuleExpression](#schemaruleexpression)]|false|true|None|
|Outputs|[[RuleOutput](#schemaruleoutput)]|false|true|None|
|ValueMappings|object|false|true|None|
|CreationTime|date-time|false|false|None|
|ModifiedTime|date-time|false|false|None|

<h2 id="tocS_RuleExpression">RuleExpression</h2>

<a id="schemaruleexpression"></a>
<a id="schema_RuleExpression"></a>
<a id="tocSruleexpression"></a>
<a id="tocsruleexpression"></a>

```json
{
  "Field": "string",
  "Pattern": "string",
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

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Field|string|false|true|None|
|Pattern|string|false|true|None|
|Specifications|[[Specification](#schemaspecification)]|false|true|None|

<h2 id="tocS_Specification">Specification</h2>

<a id="schemaspecification"></a>
<a id="schema_Specification"></a>
<a id="tocSspecification"></a>
<a id="tocsspecification"></a>

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

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[SpecificationType](#schemaspecificationtype)|false|false|None|
|Value|string|false|true|None|
|Name|string|false|true|None|
|CharacterType|[CharacterType](#schemacharactertype)|false|false|None|
|CharacterLength|int32|false|true|Null represents the longest string length within the group.|
|RequiredDelimiters|string[]|false|true|None|
|ValueMappings|object|false|true|None|

<h2 id="tocS_SpecificationType">SpecificationType</h2>

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

<h2 id="tocS_CharacterType">CharacterType</h2>

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

<h2 id="tocS_RuleOutput">RuleOutput</h2>

<a id="schemaruleoutput"></a>
<a id="schema_RuleOutput"></a>
<a id="tocSruleoutput"></a>
<a id="tocsruleoutput"></a>

```json
{
  "Field": "string",
  "Value": null
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Field|string|false|true|None|
|Value|any|false|true|None|

