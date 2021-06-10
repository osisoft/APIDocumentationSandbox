---
uid: tenant-tenants

---

# Tenants
APIs to manage an OCS Customer Tenant.

## `Get Tenant`

<a id="opIdTenant_Get Tenant"></a>

Retrieves a specific `Tenant` by ID.

### Request
```text 
GET /api/v1/Tenants/{tenantId}
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant to retrieve.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[TenantWithProperties](#schematenantwithproperties)|The `Tenant` with Id `tenantId`.|
|400|None|Could not retrieve the specified `Tenant` due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "CompanyName": "string",
  "State": 0,
  "Created": "2019-08-24T14:15:22Z",
  "LastUpdated": "2019-08-24T14:15:22Z",
  "Alias": "string",
  "Features": [
    {
      "Feature": {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "DefaultState": 0
      },
      "CurrentState": 0
    }
  ],
  "ExternalAccountId": "string",
  "Entitlements": [
    {
      "EntitlementDefinitionId": "string",
      "EntitlementType": 0,
      "LimitType": 0,
      "Value": 0,
      "ManualBlockStatus": true
    }
  ]
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Tenant Exists`

<a id="opIdTenant_Tenant Exists"></a>

Checks if a `Tenant` with a specific ID exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant for this request.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|HTTP 200 status code if a `Tenant` with `tenantId` exists.|
|400|None|Could not check if the specified `Tenant` exists due to missing or invalid input.|
|404|None|A `Tenant` with the specified ID was not found.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Update Tenant`

<a id="opIdTenant_Update Tenant"></a>

Updates a specified `Tenant` object.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant to update.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The updated details of the Tenant.<br/>

```json
{
  "Id": "string",
  "CompanyName": "string",
  "State": 0,
  "Created": "2019-08-24T14:15:22Z",
  "LastUpdated": "2019-08-24T14:15:22Z",
  "Alias": "string",
  "Features": [
    {
      "Feature": {},
      "CurrentState": 0
    }
  ],
  "ExternalAccountId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Tenant](#schematenant)|The updated `Tenant` with Id `tenantId`.|
|400|None|Could not update the `Tenant` due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "CompanyName": "string",
  "State": 0,
  "Created": "2019-08-24T14:15:22Z",
  "LastUpdated": "2019-08-24T14:15:22Z",
  "Alias": "string",
  "Features": [
    {
      "Feature": {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "DefaultState": 0
      },
      "CurrentState": 0
    }
  ],
  "ExternalAccountId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## `Get Tenant Icon`

<a id="opIdTenant_Get Tenant Icon"></a>

Returns an icon specified by its `Tenant` ID.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Icon
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant for this request.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The icon associated with the `Tenant`.|
|400|None|Could not retrieve the `Tenant` icon due to missing or invalid input.|
|403|None|Forbidden.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Create Or Update Tenant Icon`

<a id="opIdTenant_Create Or Update Tenant Icon"></a>

Creates or updates the icon for a `Tenant`. Note that the icon size must be less than `65536`.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Icon
```

#### Parameters

`string tenantId`
<br/>The Tenant identifier for this request.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The Base64 encoded PNG icon for the Tenant.<br/>

```json
"string"
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The updated Icon associated with the `Tenant`.|
|400|None|Could not create/update the `Tenant` icon due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## `Delete Tenant Icon`

<a id="opIdTenant_Delete Tenant Icon"></a>

Deletes the icon for a `Tenant`.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Icon
```

#### Parameters

`string tenantId`
<br/>The Tenant identifier for this request.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|string|HTTP status code - 200 on success, other HTTP status codes on failure.|
|400|None|Could not delete the `Tenant` icon due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Administrator</li>
</ul>

---

## `Get Regions`

<a id="opIdTenant_Get Regions"></a>

Returns the `RegionBase` list for the specified `Tenant`.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Regions
```

#### Parameters

`string tenantId`
<br/>The identifier of the Tenant for this request.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[RegionBase](#schemaregionbase)|The `RegionBase` list associated with the `Tenant`.|
|403|None|Forbidden.|
|404|None|Could not retrieve the `RegionBase` list due to tenant not found.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "AdministrativeEndpointsWritable": true,
  "BaseAddress": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### TenantWithProperties

<a id="schematenantwithproperties"></a>
<a id="schema_TenantWithProperties"></a>
<a id="tocStenantwithproperties"></a>
<a id="tocstenantwithproperties"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets identifier of this Tenant.|
|CompanyName|string|false|true|Gets or sets company Name of this Tenant.|
|State|[TenantProvisioningState](#schematenantprovisioningstate)|false|false|Gets or sets current Tenant Provisioning State for this Tenant.|
|Created|date-time|false|false|Gets or sets date and time this Tenant was added to OCS.|
|LastUpdated|date-time|false|false|Gets or sets date this Tenant was last updated.|
|Alias|string|false|true|Gets or sets specifies a unique alias for this Tenant.|
|Features|[[FeatureState](#schemafeaturestate)]|false|true|Gets or sets list of Feature States for this Tenant. Returned during get calls.|
|ExternalAccountId|string|false|true|Gets or sets the external account id for this Tenant.|
|Entitlements|[[TenantEntitlementInstance](#schematenantentitlementinstance)]|false|true|[An instance of an entitlement.]|

```json
{
  "Id": "string",
  "CompanyName": "string",
  "State": 0,
  "Created": "2019-08-24T14:15:22Z",
  "LastUpdated": "2019-08-24T14:15:22Z",
  "Alias": "string",
  "Features": [
    {
      "Feature": {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "DefaultState": 0
      },
      "CurrentState": 0
    }
  ],
  "ExternalAccountId": "string",
  "Entitlements": [
    {
      "EntitlementDefinitionId": "string",
      "EntitlementType": 0,
      "LimitType": 0,
      "Value": 0,
      "ManualBlockStatus": true
    }
  ]
}

```

---

### TenantProvisioningState

<a id="schematenantprovisioningstate"></a>
<a id="schema_TenantProvisioningState"></a>
<a id="tocStenantprovisioningstate"></a>
<a id="tocstenantprovisioningstate"></a>

Status codes describing a Tenant's current Provisioning State.

#### Enumerated Values

|Property|Value|
|---|---|
|Creating|0|
|Active|1|
|Deactivating|2|
|Deactivated|3|
|Reactivating|4|
|Deleting|5|
|Deleted|6|
|Purging|7|
|IsHomeTenant|8|

---

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

### TenantEntitlementInstance

<a id="schematenantentitlementinstance"></a>
<a id="schema_TenantEntitlementInstance"></a>
<a id="tocStenantentitlementinstance"></a>
<a id="tocstenantentitlementinstance"></a>

An instance of an entitlement.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|EntitlementDefinitionId|string|false|true|Gets or sets the identifier of the corresponding entitlement definition.|
|EntitlementType|[EntitlementType](#schemaentitlementtype)|false|false|Gets or sets the EntitlementType.|
|LimitType|[LimitType](#schemalimittype)|false|false|Gets or sets the Limit type.|
|Value|int32|false|false|Gets or sets the value.|
|ManualBlockStatus|boolean|false|false|Gets or sets the status.|

```json
{
  "EntitlementDefinitionId": "string",
  "EntitlementType": 0,
  "LimitType": 0,
  "Value": 0,
  "ManualBlockStatus": true
}

```

---

### EntitlementType

<a id="schemaentitlementtype"></a>
<a id="schema_EntitlementType"></a>
<a id="tocSentitlementtype"></a>
<a id="tocsentitlementtype"></a>

The type of entitlement.

#### Enumerated Values

|Property|Value|
|---|---|
|Feature|0|
|Resource|1|
|Usage|2|

---

### LimitType

<a id="schemalimittype"></a>
<a id="schema_LimitType"></a>
<a id="tocSlimittype"></a>
<a id="tocslimittype"></a>

The limit type of entitlement.

#### Enumerated Values

|Property|Value|
|---|---|
|Hard|0|
|Soft|1|

---

### Tenant

<a id="schematenant"></a>
<a id="schema_Tenant"></a>
<a id="tocStenant"></a>
<a id="tocstenant"></a>

Representation of a server-side database interpretation of a Tenant.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets identifier of this Tenant.|
|CompanyName|string|false|true|Gets or sets company Name of this Tenant.|
|State|[TenantProvisioningState](#schematenantprovisioningstate)|false|false|Gets or sets current Tenant Provisioning State for this Tenant.|
|Created|date-time|false|false|Gets or sets date and time this Tenant was added to OCS.|
|LastUpdated|date-time|false|false|Gets or sets date this Tenant was last updated.|
|Alias|string|false|true|Gets or sets specifies a unique alias for this Tenant.|
|Features|[[FeatureState](#schemafeaturestate)]|false|true|Gets or sets list of Feature States for this Tenant. Returned during get calls.|
|ExternalAccountId|string|false|true|Gets or sets the external account id for this Tenant.|

```json
{
  "Id": "string",
  "CompanyName": "string",
  "State": 0,
  "Created": "2019-08-24T14:15:22Z",
  "LastUpdated": "2019-08-24T14:15:22Z",
  "Alias": "string",
  "Features": [
    {
      "Feature": {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "DefaultState": 0
      },
      "CurrentState": 0
    }
  ],
  "ExternalAccountId": "string"
}

```

---

### RegionBase

<a id="schemaregionbase"></a>
<a id="schema_RegionBase"></a>
<a id="tocSregionbase"></a>
<a id="tocsregionbase"></a>

Represents a region within an OCS environment for OCS customers to see.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets the identifier for the region.|
|Name|string|false|true|Gets or sets the name associated with the region.|
|AdministrativeEndpointsWritable|boolean|false|false|Gets or sets whether administrative endpoints are writable in the region.|
|BaseAddress|string|false|true|Gets or sets the base address for the region.|

```json
{
  "Id": "string",
  "Name": "string",
  "AdministrativeEndpointsWritable": true,
  "BaseAddress": "string"
}

```

---

