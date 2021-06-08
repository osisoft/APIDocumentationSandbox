---
uid: ""

---

# Namespace
A Namespace is a collection of SDS types, streams, and stream views. Namespace identifiers are unique within a tenant. Requirements for Namespace IDs are the following: Must contain 100 characters or fewer Must only contain alphanumeric characters, underscores, dashes, spaces, and periods Must not contain two consecutive periods Must not start or end with a period Must not start with two consecutive underscores

## `List All`

<a id="opIdNamespace_List All"></a>

Returns all `Namespace`s owned by the specified `Tenant` that the caller has access to.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Namespaces
?region={region}
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>
`[optional] string region`
<br/>The region identifier in which namespaces should be filtered.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Namespace](#schemanamespace)[]|An array of `Namespace` objects for the Namespaces that belong to a tenant with `tenantId`.|
|400|None|Could not retrieve `Namespace`s due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
> 200 Response

```json
[
  {
    "Id": "string",
    "Region": "string",
    "Self": "string",
    "Description": "string",
    "State": 0,
    "Owner": {
      "Type": 1,
      "ObjectId": "string",
      "TenantId": "string"
    },
    "AccessControl": {
      "RoleTrusteeAccessControlEntries": [
        {
          "Trustee": null,
          "AccessType": null,
          "AccessRights": null
        }
      ]
    },
    "RegionId": "string",
    "InstanceId": "string"
  }
]
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Namespace By Id`

<a id="opIdNamespace_Get Namespace By Id"></a>

Returns a `Namespace` with the specified Id.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to return.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Namespace](#schemanamespace)|The `Namespace` with Id `namespaceId`.|
|400|None|Could not retrieve the `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|
|404|None|`Namespace` not found in the specified tenant.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": null,
        "AccessType": "[",
        "AccessRights": 0
      }
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Create`

<a id="opIdNamespace_Create"></a>

Creates a new `Namespace` in the specified `Tenant`.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}
?isServerTest={isServerTest}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier where the Namespace will be created.<br/><br/>`string namespaceId`
<br/>The Id of the new Namespace. The Id can also be specified in the namespaceToCreate. If it is omitted in both, the Id will be generated.<br/><br/>
`[optional] boolean isServerTest`
<br/>This parameter is unused and will be removed in the next API version.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The new Namespace to be created.<br/>

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {}
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[Namespace](#schemanamespace)|The created `Namespace`.|
|302|None|Returns the location of the existing `Namespace` object.|
|400|None|Could not create the `Namespace` due to missing or invalid input.|
|403|None|Unauthorized to create a `Namespace` in this tenant.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|
|409|None|A `Namespace` already exists with different values.|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": null,
        "AccessType": "[",
        "AccessRights": 0
      }
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Update`

<a id="opIdNamespace_Update"></a>

Updates `Namespace` information: Description and TierId. The `AccessControlList` and Owner's `Trustee` can only be updated through their own routes.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to update.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The new details to store for the Namespace.<br/>

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {}
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Namespace](#schemanamespace)|The updated `Namespace` with Id `namespaceId`.|
|400|None|Could not update the `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

#### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": null,
        "AccessType": "[",
        "AccessRights": 0
      }
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Delete`

<a id="opIdNamespace_Delete"></a>

Deletes a `Namespace` in the specified `Tenant`.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}
?isServerTest={isServerTest}
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to delete.<br/><br/>
`[optional] boolean isServerTest`
<br/>This parameter is unused and will be removed in the next API version.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|HTTP status code - 200 on success, other HTTP status codes on failure.|
|400|None|Could not delete the `Namespace` due to an invalid state.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Access Control`

<a id="opIdNamespace_Get Access Control"></a>

Returns the `AccessControlList` that is used to authorize access to a `Namespace`.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to access.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The `AccessControlList` for the Namespace with Id `namespaceId`.|
|400|None|Could not retrieve the `AccessControlList` of the specified `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
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

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Set Access Control`

<a id="opIdNamespace_Set Access Control"></a>

Updates the `AccessControlList` that is used to authorize access to a `Namespace`.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to access.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The updated AccessControlList for the Namespace.<br/>

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

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The updated `AccessControlList` for the namespace with Id `namespaceId`.|
|400|None|Could not update the `AccessControlList` of the specified `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

#### Example response body
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

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Owner`

<a id="opIdNamespace_Get Owner"></a>

Returns the Owner's `Trustee` for a given `Namespace`.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/owner
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to access.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The `Trustee` for the namespace with Id `namespaceId`.|
|400|None|Could not retrieve the Owner's `Trustee` of the specified `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|

#### Example response body
> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Set Owner`

<a id="opIdNamespace_Set Owner"></a>

Changes the Owner's `Trustee` for a given `Namespace`.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Namespaces/{namespaceId}/owner
```

#### Parameters

`string tenantId`
<br/>The identifier of the tenant to access.<br/><br/>`string namespaceId`
<br/>The identifier of the Namespace to access.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Request Body

The new Owner's Trustee of the Namespace.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The updated `Trustee` for the namespace with Id `namespaceId`.|
|400|None|Could not change the Owner's `Trustee` of the specified `Namespace` due to missing or invalid input.|
|403|None|Forbidden.|
|405|None|Method not allowed at this base URL. Try the request again at the Global base URL.|

#### Example response body
> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

### Authorization

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### Namespace

<a id="schemanamespace"></a>
<a id="schema_Namespace"></a>
<a id="tocSnamespace"></a>
<a id="tocsnamespace"></a>

Representation of a server-side database interpretation of a Namespace.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets name of this Namespace; unique within a Tenant's Namespaces.|
|Region|string|false|true|Gets or sets the region that the namespace is provisioned in.|
|Self|string|false|true|Gets or sets the namespace's URI.|
|Description|string|false|true|Gets or sets description of this Namespace.|
|State|[NamespaceProvisioningState](#schemanamespaceprovisioningstate)|false|false|Gets or sets current state of this Namespace.|
|Owner|[Trustee](#schematrustee)|false|true|Gets or sets owner Trustee of this Namespace.|
|AccessControl|[AccessControlList](#schemaaccesscontrollist)|false|true|Gets or sets the AccessControlList that defines Access Control for this Namespace.|
|RegionId|string|false|true|Gets or sets the geographic region of deployment in which the namespace is provisioned.|
|InstanceId|string|false|true|Gets or sets the Instance ID for this Namespace.|

```json
{
  "Id": "string",
  "Region": "string",
  "Self": "string",
  "Description": "string",
  "State": 0,
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": null,
        "AccessType": "[",
        "AccessRights": 0
      }
    ]
  },
  "RegionId": "string",
  "InstanceId": "string"
}

```

---

### NamespaceProvisioningState

<a id="schemanamespaceprovisioningstate"></a>
<a id="schema_NamespaceProvisioningState"></a>
<a id="tocSnamespaceprovisioningstate"></a>
<a id="tocsnamespaceprovisioningstate"></a>

Status codes describing a Namespace's current Provisioning State.

#### Enumerated Values

|Property|Value|
|---|---|
|Creating|0|
|Active|1|
|Deleting|2|
|Deleted|3|

---

### Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Type|[TrusteeType](#schematrusteetype)|false|false|None|
|ObjectId|string|false|true|None|
|TenantId|string|false|true|None|

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}

```

---

### TrusteeType

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

---

### AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

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

---

### AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Trustee|[Trustee](#schematrustee)|false|true|None|
|AccessType|[AccessType](#schemaaccesstype)|false|false|None|
|AccessRights|int64|false|false|None|

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

---

### AccessType

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

---

