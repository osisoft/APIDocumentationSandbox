---
uid: ""

---

# Tenant Feature State
APIs for managing the feature states of an OCS Tenant.

## `List All`

<a id="opIdTenantFeatureState_List All"></a>

Retrieves all `FeatureState`s for the specified `Tenant`.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Features
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[FeatureState](#schemafeaturestate)[]|An array of all `Feature`s for the tenant with Id `tenantId`.|
|400|None|Unable to retrieve `FeatureState`s due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
> 200 Response

```json
[
  {
    "Feature": {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "DefaultState": 0
    },
    "CurrentState": 0
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get`

<a id="opIdTenantFeatureState_Get"></a>

Retrieves a `FeatureState` with the specified ID from a `Tenant`.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Features/{id}
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string id`
<br/>The identifier of the FeatureState to retrieve.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[FeatureState](#schemafeaturestate)|The state of the `Feature` for the tenant with Id `tenantId`.|
|400|None|Unable to retrieve the `FeatureState` due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
> 200 Response

```json
{
  "Feature": {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "DefaultState": 0
  },
  "CurrentState": 0
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### FeatureState

<a id="schemafeaturestate"></a>
<a id="schema_FeatureState"></a>
<a id="tocSfeaturestate"></a>
<a id="tocsfeaturestate"></a>

Representation of a server-side database interpretation of a Feature State.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Feature|[Feature](#schemafeature)|false|true|Gets or sets feature for the Feature State.|
|CurrentState|int32|false|false|Gets or sets current state of the feature.|

```json
{
  "Feature": {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "DefaultState": 0
  },
  "CurrentState": 0
}

```

---

### Feature

<a id="schemafeature"></a>
<a id="schema_Feature"></a>
<a id="tocSfeature"></a>
<a id="tocsfeature"></a>

Representation of a server-side database interpretation of a Feature.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets identifier of this Feature.|
|Name|string|false|true|Gets or sets name of the Feature.|
|Description|string|false|true|Gets or sets description of the Feature.|
|DefaultState|int32|false|false|Gets or sets default state of the Feature.|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "DefaultState": 0
}

```

---

