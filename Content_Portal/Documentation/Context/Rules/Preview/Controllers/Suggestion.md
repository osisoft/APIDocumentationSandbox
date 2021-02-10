

<h1 id="context-rules-preview-controllers-suggestion-suggestion">Suggestion</h1>

## Get Suggestion

<a id="opIdSuggestion_Get Suggestion"></a>

Creates a `SuggestionResult` of a metadata `RuleModel` object.

### Request
```text 
POST /api/v1/tenants/{tenantid}/namespaces/{namespaceid}/suggestion/metadatarules
```

Sample request:
    
    POST
    {
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{Group}"
            }
        ]
    }

### Request Body

The RuleModel object to create suggestions for.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "AutomationId": "string",
  "Expressions": [
    {
      "Field": "string",
      "Pattern": "string",
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
  "ValueMappings": {
    "property1": {
      "property1": "string",
      "property2": "string"
    },
    "property2": {
      "property1": "string",
      "property2": "string"
    }
  },
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}
```

<h3 id="suggestion_get-suggestion-parameters">Parameters</h3>

`undefined tenantid`<br/>undefined<br/><br/>`undefined namespaceid`<br/>undefined<br/><br/>

<h3 id="suggestion_get-suggestion-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[SuggestionResult](#schemasuggestionresult)|A `SuggestionResult` object.|
|400|[ResponseBody](#schemaresponsebody)|Invalid rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|
|503|[ResponseBody](#schemaresponsebody)|Dependent service error.|

### Example response body

> 200 Response

```json
{
  "Results": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}
```

# Schemas

<h2 id="tocS_SuggestionResult">SuggestionResult</h2>

<a id="schemasuggestionresult"></a>
<a id="schema_SuggestionResult"></a>
<a id="tocSsuggestionresult"></a>
<a id="tocssuggestionresult"></a>

```json
{
  "Results": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|object|false|true|None|

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

<h2 id="tocS_RuleModel">RuleModel</h2>

<a id="schemarulemodel"></a>
<a id="schema_RuleModel"></a>
<a id="tocSrulemodel"></a>
<a id="tocsrulemodel"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "AutomationId": "string",
  "Expressions": [
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
  ],
  "Outputs": [
    {
      "Field": "string",
      "Value": null
    }
  ],
  "ValueMappings": {
    "property1": {
      "property1": "string",
      "property2": "string"
    },
    "property2": {
      "property1": "string",
      "property2": "string"
    }
  },
  "CreationTime": "2019-08-24T14:15:22Z",
  "ModifiedTime": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
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

|Name|Type|Required|Nullable|Description|
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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[SpecificationType](#schemaspecificationtype)|false|false|None|
|Value|string|false|true|None|
|Name|string|false|true|None|
|CharacterType|[CharacterType](#schemacharactertype)|false|false|None|
|CharacterLength|int32|false|true|None|
|RequiredDelimiters|List of strings|false|true|None|
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

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Field|string|false|true|None|
|Value|any|false|true|None|

