---
title: Assets/assets v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="assets-assets-assets">Assets</h1>

	

	

	

	

	

	

	

	

	

	

	

	

---
## Get Assets

<a id="opIdAssets_Get Assets"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets
```

<h3 id="assets_get-assets-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] integer skip`<br/><br/>`[optional] integer count`<br/><br/>`[optional] string orderBy`<br/><br/>`[optional] string query`<br/><br/>

<h3 id="assets_get-assets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Create Assets

<a id="opIdAssets_Create Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets
```

### Request Body

<br/>

```json
[
  {
    "Id": "string",
    "AssetTypeId": "string",
    "Name": "string",
    "Description": "string",
    "Metadata": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "SdsTypeCode": "Empty",
        "Value": null,
        "Uom": "string"
      }
    ],
    "StreamReferences": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "StreamId": "string"
      }
    ],
    "Status": {
      "Name": "string",
      "Description": "string",
      "StreamReferenceId": "string",
      "StreamPropertyId": "string",
      "ValueStatusMappings": [
        {
          "Value": null,
          "Status": null,
          "DisplayName": null
        }
      ]
    }
  }
]
```

<h3 id="assets_create-assets-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_create-assets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Asset By Id

<a id="opIdAssets_Get Asset By Id"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}
```

<h3 id="assets_get-asset-by-id-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_get-asset-by-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Create Asset

<a id="opIdAssets_Create Asset"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}
```

### Request Body

<br/>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "Name": "string",
    "Description": "string",
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {}
    ]
  }
}
```

<h3 id="assets_create-asset-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_create-asset-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Create Or Update Asset

<a id="opIdAssets_Create Or Update Asset"></a>

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}
```

### Request Body

<br/>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "Name": "string",
    "Description": "string",
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {}
    ]
  }
}
```

<h3 id="assets_create-or-update-asset-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_create-or-update-asset-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Delete Asset

<a id="opIdAssets_Delete Asset"></a>

### Request
```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}
```

<h3 id="assets_delete-asset-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_delete-asset-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Asset Acl

<a id="opIdAssets_Get Asset Acl"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/accesscontrol
```

<h3 id="assets_get-asset-acl-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_get-asset-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Update Asset Access Control

<a id="opIdAssets_Update Asset Access Control"></a>

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/accesscontrol
```

### Request Body

<br/>

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

<h3 id="assets_update-asset-access-control-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string assetId`<br/><br/>

<h3 id="assets_update-asset-access-control-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Asset Access Rights

<a id="opIdAssets_Get Asset Access Rights"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/accessrights
```

<h3 id="assets_get-asset-access-rights-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_get-asset-access-rights-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Asset Owner

<a id="opIdAssets_Get Asset Owner"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/owner
```

<h3 id="assets_get-asset-owner-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_get-asset-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Update Asset Owner

<a id="opIdAssets_Update Asset Owner"></a>

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/owner
```

### Request Body

<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

<h3 id="assets_update-asset-owner-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string assetId`<br/><br/>

<h3 id="assets_update-asset-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Delete Assets

<a id="opIdAssets_Delete Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/delete
```

### Request Body

<br/>

```json
[
  "string"
]
```

<h3 id="assets_delete-assets-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assets_delete-assets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Assets In Search Result Format

<a id="opIdAssets_Get Assets In Search Result Format"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/search/assets
```

<h3 id="assets_get-assets-in-search-result-format-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] integer skip`<br/><br/>`[optional] integer count`<br/><br/>`[optional] string orderBy`<br/><br/>`[optional] string query`<br/><br/>

<h3 id="assets_get-assets-in-search-result-format-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

# Definitions

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

|Property Name|Data Type|Required|Nullable|Description|
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

|Property Name|Data Type|Required|Nullable|Description|
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

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Trustee|[Trustee](#schematrustee)|false|true|None|
|AccessType|[AccessType](#schemaaccesstype)|false|false|None|
|AccessRights|int64|false|false|None|

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

<h2 id="tocS_AssetDto">AssetDto</h2>

<a id="schemaassetdto"></a>
<a id="schema_AssetDto"></a>
<a id="tocSassetdto"></a>
<a id="tocsassetdto"></a>

```json
{
  "Id": "string",
  "AssetTypeId": "string",
  "Name": "string",
  "Description": "string",
  "Metadata": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "SdsTypeCode": "Empty",
      "Value": null,
      "Uom": "string"
    }
  ],
  "StreamReferences": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "StreamId": "string"
    }
  ],
  "Status": {
    "Name": "string",
    "Description": "string",
    "StreamReferenceId": "string",
    "StreamPropertyId": "string",
    "ValueStatusMappings": [
      {
        "Value": null,
        "Status": "[",
        "DisplayName": "string"
      }
    ]
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|AssetTypeId|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|Metadata|[[MetadataDto](#schemametadatadto)]|false|true|None|
|StreamReferences|[[StreamReferenceDto](#schemastreamreferencedto)]|false|true|None|
|Status|[StatusMappingDto](#schemastatusmappingdto)|false|true|None|

<h2 id="tocS_MetadataDto">MetadataDto</h2>

<a id="schemametadatadto"></a>
<a id="schema_MetadataDto"></a>
<a id="tocSmetadatadto"></a>
<a id="tocsmetadatadto"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "SdsTypeCode": "Empty",
  "Value": null,
  "Uom": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|SdsTypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Value|any|false|true|None|
|Uom|string|false|true|None|

<h2 id="tocS_SdsTypeCode">SdsTypeCode</h2>

<a id="schemasdstypecode"></a>
<a id="schema_SdsTypeCode"></a>
<a id="tocSsdstypecode"></a>
<a id="tocssdstypecode"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Empty|Empty|
|Object|Object|
|Boolean|Boolean|
|Char|Char|
|SByte|SByte|
|Byte|Byte|
|Int16|Int16|
|UInt16|UInt16|
|Int32|Int32|
|UInt32|UInt32|
|Int64|Int64|
|UInt64|UInt64|
|Single|Single|
|Double|Double|
|Decimal|Decimal|
|DateTime|DateTime|
|String|String|
|Guid|Guid|
|DateTimeOffset|DateTimeOffset|
|TimeSpan|TimeSpan|
|Version|Version|
|NullableBoolean|NullableBoolean|
|NullableChar|NullableChar|
|NullableSByte|NullableSByte|
|NullableByte|NullableByte|
|NullableInt16|NullableInt16|
|NullableUInt16|NullableUInt16|
|NullableInt32|NullableInt32|
|NullableUInt32|NullableUInt32|
|NullableInt64|NullableInt64|
|NullableUInt64|NullableUInt64|
|NullableSingle|NullableSingle|
|NullableDouble|NullableDouble|
|NullableDecimal|NullableDecimal|
|NullableDateTime|NullableDateTime|
|NullableGuid|NullableGuid|
|NullableDateTimeOffset|NullableDateTimeOffset|
|NullableTimeSpan|NullableTimeSpan|
|BooleanArray|BooleanArray|
|CharArray|CharArray|
|SByteArray|SByteArray|
|ByteArray|ByteArray|
|Int16Array|Int16Array|
|UInt16Array|UInt16Array|
|Int32Array|Int32Array|
|UInt32Array|UInt32Array|
|Int64Array|Int64Array|
|UInt64Array|UInt64Array|
|SingleArray|SingleArray|
|DoubleArray|DoubleArray|
|DecimalArray|DecimalArray|
|DateTimeArray|DateTimeArray|
|StringArray|StringArray|
|GuidArray|GuidArray|
|DateTimeOffsetArray|DateTimeOffsetArray|
|TimeSpanArray|TimeSpanArray|
|VersionArray|VersionArray|
|Array|Array|
|IList|IList|
|IDictionary|IDictionary|
|IEnumerable|IEnumerable|
|SdsType|SdsType|
|SdsTypeProperty|SdsTypeProperty|
|SdsStreamView|SdsStreamView|
|SdsStreamViewProperty|SdsStreamViewProperty|
|SdsStreamViewMap|SdsStreamViewMap|
|SdsStreamViewMapProperty|SdsStreamViewMapProperty|
|SdsStream|SdsStream|
|SdsStreamIndex|SdsStreamIndex|
|SdsTable|SdsTable|
|SdsColumn|SdsColumn|
|SdsValues|SdsValues|
|SdsObject|SdsObject|
|SByteEnum|SByteEnum|
|ByteEnum|ByteEnum|
|Int16Enum|Int16Enum|
|UInt16Enum|UInt16Enum|
|Int32Enum|Int32Enum|
|UInt32Enum|UInt32Enum|
|Int64Enum|Int64Enum|
|UInt64Enum|UInt64Enum|
|NullableSByteEnum|NullableSByteEnum|
|NullableByteEnum|NullableByteEnum|
|NullableInt16Enum|NullableInt16Enum|
|NullableUInt16Enum|NullableUInt16Enum|
|NullableInt32Enum|NullableInt32Enum|
|NullableUInt32Enum|NullableUInt32Enum|
|NullableInt64Enum|NullableInt64Enum|
|NullableUInt64Enum|NullableUInt64Enum|

<h2 id="tocS_StreamReferenceDto">StreamReferenceDto</h2>

<a id="schemastreamreferencedto"></a>
<a id="schema_StreamReferenceDto"></a>
<a id="tocSstreamreferencedto"></a>
<a id="tocsstreamreferencedto"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "StreamId": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|StreamId|string|true|false|None|

<h2 id="tocS_StatusMappingDto">StatusMappingDto</h2>

<a id="schemastatusmappingdto"></a>
<a id="schema_StatusMappingDto"></a>
<a id="tocSstatusmappingdto"></a>
<a id="tocsstatusmappingdto"></a>

```json
{
  "Name": "string",
  "Description": "string",
  "StreamReferenceId": "string",
  "StreamPropertyId": "string",
  "ValueStatusMappings": [
    {
      "Value": null,
      "Status": 0,
      "DisplayName": "string"
    }
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|None|
|Description|string|false|true|None|
|StreamReferenceId|string|true|false|None|
|StreamPropertyId|string|true|false|None|
|ValueStatusMappings|[[ValueStatusMappingDto](#schemavaluestatusmappingdto)]|false|true|None|

<h2 id="tocS_ValueStatusMappingDto">ValueStatusMappingDto</h2>

<a id="schemavaluestatusmappingdto"></a>
<a id="schema_ValueStatusMappingDto"></a>
<a id="tocSvaluestatusmappingdto"></a>
<a id="tocsvaluestatusmappingdto"></a>

```json
{
  "Value": null,
  "Status": 0,
  "DisplayName": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|any|false|true|None|
|Status|[StatusEnum](#schemastatusenum)|true|false|None|
|DisplayName|string|false|true|None|

<h2 id="tocS_StatusEnum">StatusEnum</h2>

<a id="schemastatusenum"></a>
<a id="schema_StatusEnum"></a>
<a id="tocSstatusenum"></a>
<a id="tocsstatusenum"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Unknown|0|
|Good|1|
|Warning|2|
|Bad|3|

