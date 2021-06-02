---
uid: ""

---

# Rules Main Controller Base
Interacts with the IRuleStore and IAuthorizationService to process requests.

## `List Rules`

<a id="opIdRulesMainControllerBase_List Rules"></a>

Gets all `RuleModel` objects from the `IRuleStore` the requesting `Identity` has access to.

### Request
```text 
GET /api/v1/RulesMainBase
?Skip={Skip}&Count={Count}&KeepOldMetadata={KeepOldMetadata}
```

#### Parameters

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
|200|[RuleModel](#schemarulemodel)[]|The `RuleModel` objects.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 200 Response

```json
[
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
            "Type": "[",
            "Value": "string",
            "Name": "string",
            "CharacterType": "[",
            "CharacterLength": 0,
            "RequiredDelimiters": [
              null
            ],
            "ValueMappings": {}
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

<a id="opIdRulesMainControllerBase_Create Rule With Server Generated Id"></a>

Creates a `RuleModel` object with a server generated `Id` in the `IRuleStore`.

### Request
```text 
POST /api/v1/RulesMainBase
```

#### Parameters

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The RuleModel object to create.<br/>

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
|201|[RuleModel](#schemarulemodel)|A link to the `RuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the same id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

#### Example response body
> 201 Response

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
## Definitions

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

