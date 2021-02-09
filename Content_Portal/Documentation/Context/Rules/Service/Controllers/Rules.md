

<h1 id="context-rules-service-controllers-rules-rules">Rules</h1>

## Search Rules

<a id="opIdRules_Search Rules"></a>

Gets all `RuleModel` objects from the `IRuleStore` the requesting `Identity` has access to.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules
```

<h3 id="rules_search-rules-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_search-rules-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [RuleModel](#schemarulemodel)s|The `RuleModel` objects.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Create Rule With Server Generated Id2

<a id="opIdRules_Create Rule With Server Generated Id2"></a>

Creates a `RuleModel` object with a server generated `Id` in the `IRuleStore` .

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules
```

Sample request:

    POST
    {
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object to create.<br/>

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

<h3 id="rules_create-rule-with-server-generated-id2-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="rules_create-rule-with-server-generated-id2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|string|A link to the `RuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the same id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Get Rule2

<a id="opIdRules_Get Rule2"></a>

Gets the specifed rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

<h3 id="rules_get-rule2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_get-rule2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RuleModel](#schemarulemodel)|The specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

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

## Create Rule2

<a id="opIdRules_Create Rule2"></a>

Gets or creates a `RuleModel` object with the specified id in the `IRuleStore` .

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

Sample request:

    POST /sampleId
    {
        "Id": "sampleId",
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object.<br/>

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

<h3 id="rules_create-rule2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_create-rule2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|None|A link to the `RuleModel` object.|
|302|None|An equivalent rule with the same id and defintion already exists.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|None|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the specified id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Create Or Update Rule2

<a id="opIdRules_Create Or Update Rule2"></a>

Creates or updates the specified rule in the `IRuleStore` .

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

Sample request:

    PUT /sampleId
    {
        "Id": "sampleId",
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object to create or update.<br/>

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

<h3 id="rules_create-or-update-rule2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_create-or-update-rule2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RuleModel](#schemarulemodel)|The updated `RuleModel` object or a link to the new `RuleModel` object.|
|201|None|The updated `RuleModel` object or a link to the new `RuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

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

## Delete Rule2

<a id="opIdRules_Delete Rule2"></a>

Deletes the specifed rule from the `IRuleStore` .

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}
```

<h3 id="rules_delete-rule2-parameters">Parameters</h3>

`undefined routeOptions`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_delete-rule2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specifed rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Execute Rule2

<a id="opIdRules_Execute Rule2"></a>

Executes the specified rule.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/execute
```

<h3 id="rules_execute-rule2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_execute-rule2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Search Rules All

<a id="opIdRules_Search Rules All"></a>

Gets all `RuleModel` objects from the `IRuleStore` the requesting `Identity` has access to.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules
```

<h3 id="rules_search-rules-all-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_search-rules-all-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [RuleModel](#schemarulemodel)s|The `RuleModel` objects.|
|400|[ResponseBody](#schemaresponsebody)|Invalid uri query parameters.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Create Rule With Server Generated Id

<a id="opIdRules_Create Rule With Server Generated Id"></a>

Creates a `RuleModel` object with a server generated `Id` in the `IRuleStore` .

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules
```

Sample request:

    POST
    {
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object to create.<br/>

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

<h3 id="rules_create-rule-with-server-generated-id-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="rules_create-rule-with-server-generated-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|string|A link to the `RuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the same id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Get Rule

<a id="opIdRules_Get Rule"></a>

Gets the specifed rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}
```

<h3 id="rules_get-rule-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_get-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RuleModel](#schemarulemodel)|The specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

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

## Create Rule

<a id="opIdRules_Create Rule"></a>

Gets or creates a `RuleModel` object with the specified id in the `IRuleStore` .

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}
```

Sample request:

    POST /sampleId
    {
        "Id": "sampleId",
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object.<br/>

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

<h3 id="rules_create-rule-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_create-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|None|A link to the `RuleModel` object.|
|302|None|An equivalent rule with the same id and defintion already exists.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|None|
|409|[ResponseBody](#schemaresponsebody)|A non-equivalent rule with the specified id already exists.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Create Or Update Rule

<a id="opIdRules_Create Or Update Rule"></a>

Creates or updates the specified rule in the `IRuleStore` .

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}
```

Sample request:

    PUT /sampleId
    {
        "Id": "sampleId",
        "Name": "sample rule",
        "Description": "a sample rule description",
        "AutomationId": "{automationId}",
        "Expressions": [
            {
                "Field": "Name",
                "Pattern": "{streamName}"
            }
        ],
        "Outputs": [
            {
                "Field": "Metadata",
                "Value": {
                    "key": "{streamName}"
                }
            }
        ]
    }

### Request Body

The RuleModel object to create or update.<br/>

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

<h3 id="rules_create-or-update-rule-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_create-or-update-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[RuleModel](#schemarulemodel)|The updated `RuleModel` object or a link to the new `RuleModel` object.|
|201|None|The updated `RuleModel` object or a link to the new `RuleModel` object.|
|400|[ResponseBody](#schemaresponsebody)|The rule is malformed or invalid.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

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

## Delete Rule

<a id="opIdRules_Delete Rule"></a>

Deletes the specifed rule from the `IRuleStore` .

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}
```

<h3 id="rules_delete-rule-parameters">Parameters</h3>

`undefined routeOptions`<br/>undefined<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>
`[optional] integer Skip`<br/>An Int32 to determine how many results to skip. Defaults to DefaultSkip<br/><br/>`[optional] integer Count`<br/>An Int32 to determine how many results to return. Defaults to DefaultCount<br/><br/>`[optional] boolean KeepOldMetadata`<br/>A Boolean to determine whether or not existing metadata should be kept.<br/><br/>

#### Detailed descriptions

**KeepOldMetadata**: A Boolean to determine whether or not existing metadata should be kept.
Defaults to false.

<h3 id="rules_delete-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specifed rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

## Execute Rule

<a id="opIdRules_Execute Rule"></a>

Executes the specified rule.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/execute
```

<h3 id="rules_execute-rule-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="rules_execute-rule-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

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

<h2 id="tocS_RuleRouteOptions">RuleRouteOptions</h2>

<a id="schemarulerouteoptions"></a>
<a id="schema_RuleRouteOptions"></a>
<a id="tocSrulerouteoptions"></a>
<a id="tocsrulerouteoptions"></a>

```json
{
  "RuleId": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RuleId|string|false|true|The id of a rule.|

