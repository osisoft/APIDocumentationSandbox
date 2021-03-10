---
title: Assets/resolved-asset-data v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="assets-resolved-asset-data-resolved-asset-data">Resolved Asset Data</h1>

---
## Get Window Data

<a id="opIdResolvedAssetData_Get Window Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/Data
```

<h3 id="resolvedassetdata_get-window-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string startIndex`<br/><br/>`string endIndex`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] array stream`<br/><br/>

<h3 id="resolvedassetdata_get-window-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Interpolated Data

<a id="opIdResolvedAssetData_Get Interpolated Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/Data/Interpolated
```

<h3 id="resolvedassetdata_get-interpolated-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string startIndex`<br/><br/>`string endIndex`<br/><br/>`integer count`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] array stream`<br/><br/>

<h3 id="resolvedassetdata_get-interpolated-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Last Data

<a id="opIdResolvedAssetData_Get Last Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/Data/Last
```

<h3 id="resolvedassetdata_get-last-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] array stream`<br/><br/>

<h3 id="resolvedassetdata_get-last-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Sampled Data

<a id="opIdResolvedAssetData_Get Sampled Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/Data/Sampled
```

<h3 id="resolvedassetdata_get-sampled-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string startIndex`<br/><br/>`string endIndex`<br/><br/>`integer intervals`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] array stream`<br/><br/>

<h3 id="resolvedassetdata_get-sampled-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Get Summary Data

<a id="opIdResolvedAssetData_Get Summary Data"></a>

### Request
```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/assets/{assetId}/Data/Summaries
```

<h3 id="resolvedassetdata_get-summary-data-parameters">Parameters</h3>

`string assetId`<br/><br/>`string startIndex`<br/><br/>`string endIndex`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] array stream`<br/><br/>`[optional] integer count`<br/><br/>

<h3 id="resolvedassetdata_get-summary-data-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

