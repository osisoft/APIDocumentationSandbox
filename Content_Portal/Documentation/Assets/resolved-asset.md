---
title: Assets/resolved-asset v20210310.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="assets-resolved-asset-resolved-asset">Resolved Asset</h1>

---
## Bulk Get Resolved Assets

<a id="opIdResolvedAsset_Bulk Get Resolved Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/resolved
```

### Request Body

<br/>

```json
[
  "string"
]
```

<h3 id="resolvedasset_bulk-get-resolved-assets-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>
`[optional] string shapeId`<br/><br/>

<h3 id="resolvedasset_bulk-get-resolved-assets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

