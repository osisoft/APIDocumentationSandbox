---
title: Assets/collection-acls v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="assets-collection-acls-collection-acls">Collection Acls</h1>

	

	

	

	

	

---
## Get Collection Acl

<a id="opIdCollectionAcls_Get Collection Acl"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/{resource}
```

<h3 id="collectionacls_get-collection-acl-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string resource`<br/><br/>

<h3 id="collectionacls_get-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Update Collection Acl

<a id="opIdCollectionAcls_Update Collection Acl"></a>

### Request
```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/{resource}
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

<h3 id="collectionacls_update-collection-acl-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string resource`<br/><br/>

<h3 id="collectionacls_update-collection-acl-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Collection Access Rights

<a id="opIdCollectionAcls_Get Collection Access Rights"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/accessrights/{resource}
```

<h3 id="collectionacls_get-collection-access-rights-parameters">Parameters</h3>

`string resource`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="collectionacls_get-collection-access-rights-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

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

