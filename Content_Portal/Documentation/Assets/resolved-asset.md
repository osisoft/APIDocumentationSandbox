---
title: Assets/resolved-asset v20210311.1
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.6

---

[[_TOC_]]

# Resolved Asset

## Bulk Get Resolved Assets

<a id="opIdResolvedAsset_Bulk Get Resolved Assets"></a>

### Request
```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/bulk/assets/resolved
?shapeId={shapeId}
```

### Request Body

<br/>

```json
[
  "string"
]
```

### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] string shapeId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

