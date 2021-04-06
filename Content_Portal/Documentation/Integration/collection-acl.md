---
title: Integration/collection-acl v20210405.11
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Collection Acl

## Get

<a id="opIdCollectionAcl_Get"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/dataviews
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|None|
|403|string|None|
|500|[Exception](#schemaexception)|None|

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

---

## Update

<a id="opIdCollectionAcl_Update"></a>

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accesscontrol/dataviews
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

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

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|None|
|400|string|None|
|403|string|None|
|500|[Exception](#schemaexception)|None|

#### Example response body
> 500 Response

```json
{
  "StackTrace": "string",
  "Message": "string",
  "InnerException": {
    "StackTrace": "string",
    "Message": "string",
    "InnerException": {
      "StackTrace": null,
      "Message": null,
      "InnerException": null,
      "Source": null
    },
    "Source": "string"
  },
  "Source": "string"
}
```

---
# Definitions

## AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

### Properties

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

## AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

### Properties

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

## Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

### Properties

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

## TrusteeType

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

## AccessType

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

## Exception

<a id="schemaexception"></a>
<a id="schema_Exception"></a>
<a id="tocSexception"></a>
<a id="tocsexception"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StackTrace|string|false|true|None|
|Message|string|false|false|None|
|InnerException|[Exception](#schemaexception)|false|true|None|
|Source|string|false|true|None|

```json
{
  "StackTrace": "string",
  "Message": "string",
  "InnerException": {
    "StackTrace": "string",
    "Message": "string",
    "InnerException": {
      "StackTrace": null,
      "Message": null,
      "InnerException": null,
      "Source": null
    },
    "Source": "string"
  },
  "Source": "string"
}

```

---

