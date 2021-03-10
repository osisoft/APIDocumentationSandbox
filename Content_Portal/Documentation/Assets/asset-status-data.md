---
title: Assets/asset-status-data v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="assets-asset-status-data-asset-status-data">Asset Status Data</h1>

---
## Get Last Asset Status Data

<a id="opIdAssetStatusData_Get Last Asset Status Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/status/last
```

<h3 id="assetstatusdata_get-last-asset-status-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assetstatusdata_get-last-asset-status-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Last Status Data For Assets Bulk

<a id="opIdAssetStatusData_Get Last Status Data For Assets Bulk"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/status/last
```

### Request Body

<br/>

```json
[
  "string"
]
```

<h3 id="assetstatusdata_get-last-status-data-for-assets-bulk-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="assetstatusdata_get-last-status-data-for-assets-bulk-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

