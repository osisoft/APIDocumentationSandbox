---
title: PITo-Ocs/access-control v20210310.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="pito-ocs-access-control-access-control">Access Control</h1>

	

	

	

	

	

	

---
## Get Data Sources Collection Acl

<a id="opIdAccessControl_Get Data Sources Collection Acl"></a>

Get `AccessControlList` object for the DataSources collection.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/AccessControl/DataSources
```

<h3 id="accesscontrol_get-data-sources-collection-acl-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_get-data-sources-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|AccessControlList|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

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

---
## Modify Data Sources Collection Acl

<a id="opIdAccessControl_Modify Data Sources Collection Acl"></a>

Update DataSources collection Access Control List with `newAccessControlList`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/AccessControl/DataSources
```

### Request Body

The new Access Control List that the DataSources collection will be updated with.<br/>

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

<h3 id="accesscontrol_modify-data-sources-collection-acl-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_modify-data-sources-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|IActionResult|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---
## Get Data Source Acl

<a id="opIdAccessControl_Get Data Source Acl"></a>

Get `AccessControlList` object for the DataSource specified by `dataSourceId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/AccessControl
```

<h3 id="accesscontrol_get-data-source-acl-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the specified DataSource.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_get-data-source-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|AccessControlList|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

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

---
## Modify Data Source Acl

<a id="opIdAccessControl_Modify Data Source Acl"></a>

Update Access Control List for the DataSource specified by `dataSourceId` with `newAcl`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/AccessControl
```

### Request Body

The new Access Control List that the specified DataSource will be updated with.<br/>

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

<h3 id="accesscontrol_modify-data-source-acl-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the specified DataSource.<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_modify-data-source-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|IActionResult|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

---
## Get Data Source Owner

<a id="opIdAccessControl_Get Data Source Owner"></a>

Get `Trustee` object for the DataSource specified by `dataSourceId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/Owner
```

<h3 id="accesscontrol_get-data-source-owner-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the specified DataSource.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_get-data-source-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|Trustee|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

---
## Modify Data Source Owner

<a id="opIdAccessControl_Modify Data Source Owner"></a>

Update the Owner for the DataSource specified by `dataSourceId` with `newOwner`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/Owner
```

### Request Body

The new Owner that the specified DataSource will be updated with.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

<h3 id="accesscontrol_modify-data-source-owner-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the namespace belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the specified DataSource.<br/><br/>`string namespaceId`<br/><br/>

<h3 id="accesscontrol_modify-data-source-owner-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|IActionResult|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}
```

# Definitions

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

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "property1": null,
  "property2": null
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|

