

<h1 id="context-rules-service-controllers-acl-acl">Acl</h1>

## Get Collection Acl2

<a id="opIdAcl_Get Collection Acl2"></a>

Gets the `AccessControlList` for the rules collection.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/assetrules
```

<h3 id="acl_get-collection-acl2-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="acl_get-collection-acl2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The `AccessControlList` for the rules collection.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Set Collection Acl2

<a id="opIdAcl_Set Collection Acl2"></a>

Replaces the `AccessControlList` for the rules collection.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/assetrules
```

Sample request:
    
    PUT /accesscontrol/metadatarules
    {
        "RoleTrusteeAccessControlEntries": [
            {
                "Trustee": {
                    "Type": 3,
                    "ObjectId": "13c3324c-afab-4519-99af-568b56b971cc"
                },
                "AccessType: 0,
                "AccessRights": 15
            }
        ]
    }

### Request Body

The ACL.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

<h3 id="acl_set-collection-acl2-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="acl_set-collection-acl2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The new `AccessControlList` for the rules collection.|
|400|[ResponseBody](#schemaresponsebody)|An invalid access control list.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Get Collection Acl

<a id="opIdAcl_Get Collection Acl"></a>

Gets the `AccessControlList` for the rules collection.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/metadatarules
```

<h3 id="acl_get-collection-acl-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="acl_get-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The `AccessControlList` for the rules collection.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Set Collection Acl

<a id="opIdAcl_Set Collection Acl"></a>

Replaces the `AccessControlList` for the rules collection.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/metadatarules
```

Sample request:
    
    PUT /accesscontrol/metadatarules
    {
        "RoleTrusteeAccessControlEntries": [
            {
                "Trustee": {
                    "Type": 3,
                    "ObjectId": "13c3324c-afab-4519-99af-568b56b971cc"
                },
                "AccessType: 0,
                "AccessRights": 15
            }
        ]
    }

### Request Body

The ACL.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

<h3 id="acl_set-collection-acl-parameters">Parameters</h3>

`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>

<h3 id="acl_set-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The new `AccessControlList` for the rules collection.|
|400|[ResponseBody](#schemaresponsebody)|An invalid access control list.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Get Acl2

<a id="opIdAcl_Get Acl2"></a>

Gets the `AccessControlList` of the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/accesscontrol
```

<h3 id="acl_get-acl2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="acl_get-acl2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The `AccessControlList` of the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Set Acl2

<a id="opIdAcl_Set Acl2"></a>

Replaces the `AccessControlList` of the specified rule.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/assetrules/{ruleId}/accesscontrol
```

Sample request:
    
    PUT /sampleId/accesscontrol
    {
        "RoleTrusteeAccessControlEntries": [
            {
                "Trustee": {
                    "Type": 3,
                    "ObjectId": "13c3324c-afab-4519-99af-568b56b971cc"
                },
                "AccessType: 0,
                "AccessRights": 15
            }
        ]
    }

### Request Body

The ACL object.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

<h3 id="acl_set-acl2-parameters">Parameters</h3>

`undefined routeOptions`<br/>The uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="acl_set-acl2-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The new `AccessControlList` .|
|400|[ResponseBody](#schemaresponsebody)|An invalid access control list.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Get Acl

<a id="opIdAcl_Get Acl"></a>

Gets the `AccessControlList` of the specified rule.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/accesscontrol
```

<h3 id="acl_get-acl-parameters">Parameters</h3>

`undefined routeOptions`<br/>The RuleRouteOptions uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="acl_get-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The `AccessControlList` of the specified rule.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

## Set Acl

<a id="opIdAcl_Set Acl"></a>

Replaces the `AccessControlList` of the specified rule.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/metadatarules/{ruleId}/accesscontrol
```

Sample request:
    
    PUT /sampleId/accesscontrol
    {
        "RoleTrusteeAccessControlEntries": [
            {
                "Trustee": {
                    "Type": 3,
                    "ObjectId": "13c3324c-afab-4519-99af-568b56b971cc"
                },
                "AccessType: 0,
                "AccessRights": 15
            }
        ]
    }

### Request Body

The ACL object.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

<h3 id="acl_set-acl-parameters">Parameters</h3>

`undefined routeOptions`<br/>The uri route parameters.<br/><br/>`undefined tenantId`<br/>undefined<br/><br/>`undefined namespaceId`<br/>undefined<br/><br/>`undefined ruleId`<br/>undefined<br/><br/>

<h3 id="acl_set-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The new `AccessControlList` .|
|400|[ResponseBody](#schemaresponsebody)|An invalid access control list.|
|403|[ResponseBody](#schemaresponsebody)|Forbidden.|
|404|[ResponseBody](#schemaresponsebody)|The specified rule was not found.|
|500|[ResponseBody](#schemaresponsebody)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

# Schemas

<h2 id="tocS_AccessControlList">AccessControlList</h2>

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
        "ObjectId": "string",
        "TenantId": "string"
      },
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

<h2 id="tocS_AccessControlEntry">AccessControlEntry</h2>

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

```json
{
  "Trustee": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessType": 0,
  "AccessRights": 0
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Trustee|[Trustee](#schematrustee)|false|true|None|
|AccessType|[AccessType](#schemaaccesstype)|false|false|None|
|AccessRights|int64|false|false|None|

<h2 id="tocS_Trustee">Trustee</h2>

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[TrusteeType](#schematrusteetype)|false|false|None|
|ObjectId|string|false|true|None|
|TenantId|string|false|true|None|

<h2 id="tocS_TrusteeType">TrusteeType</h2>

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

<h2 id="tocS_AccessType">AccessType</h2>

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

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

