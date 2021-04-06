---
title: Integration/collection-access-rights v20210406.12
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Collection Access Rights
API for retrieving access rights on the data views collection

## List

<a id="opIdCollectionAccessRights_List"></a>

Get the calling user or client's access rights on the data views collection

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accessrights/dataviews
```

#### Parameters

`string tenantId`
<br/>The tenant identifier.<br/><br/>`string namespaceId`
<br/>The namespace identifier.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A list of access rights to the data views collection.|
|403|[ResultError](#schemaresulterror)|You are not authorized to view the requested data view collection's access control list.|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.|

#### Example response body
> 200 Response

```json
[
  "Read",
  "Write",
  "Delete",
  "ManageAccessControl"
]
```

> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}
```

---
# Definitions

## ResultError

<a id="schemaresulterror"></a>
<a id="schema_ResultError"></a>
<a id="tocSresulterror"></a>
<a id="tocsresulterror"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Kind|[ResultErrorKind](#schemaresulterrorkind)|false|false|None|
|Parameters|object|false|true|None|
|ChildErrors|[[ResultError](#schemaresulterror)]|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}

```

---

## ResultErrorKind

<a id="schemaresulterrorkind"></a>
<a id="schema_ResultErrorKind"></a>
<a id="tocSresulterrorkind"></a>
<a id="tocsresulterrorkind"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|UnspecifiedServerError|0|
|RequestInvalid|1|
|ResourceNotFound|2|
|OperationForbidden|3|
|OperationInvalid|4|
|OperationFailed|5|
|ResourceUnavailable|6|

---

