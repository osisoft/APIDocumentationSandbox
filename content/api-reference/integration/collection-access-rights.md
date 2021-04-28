

# Collection Access Rights
APIs for retrieving access rights on the data views collection<br/>

## `List Data Views Access Rights`

<a id="opIdCollectionAccessRights_List Data Views Access Rights"></a>

Gets the access rights to the data views collection for the calling user or client<br/>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/accessrights/dataviews
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A list of access rights to the data views collection<br/>|
|403|[ErrorResponse](#schemaerrorresponse)|You are not authorized to view the requested data view collection's access control list<br/>|
|500|[ErrorResponse](#schemaerrorresponse)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
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
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}
```

---
## Definitions

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Parameters|object|false|true|None|
|ChildErrors|object|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": {
    "property1": null,
    "property2": null
  }
}

```

---

