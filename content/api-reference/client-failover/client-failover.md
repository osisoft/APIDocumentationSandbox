---
uid: ""

---

# Client Failover
API for Client Failover application information.

## `Get Information`

<a id="opIdClientFailover_Get Information"></a>

Gets the Client Failover application information.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[FailoverEndpointInfo](#schemafailoverendpointinfo)|The result of the GET operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|

<h4>Example response body</h4>

> 200 Response ([FailoverEndpointInfo](#schemafailoverendpointinfo))

```json
{
  "Version": "string"
}
```

---
## Definitions

### FailoverEndpointInfo

<a id="schemafailoverendpointinfo"></a>
<a id="schema_FailoverEndpointInfo"></a>
<a id="tocSfailoverendpointinfo"></a>
<a id="tocsfailoverendpointinfo"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Version|string|false|true|None|

```json
{
  "Version": "string"
}

```

---

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

Response error for controller methods.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|Operation identifier|
|Error|string|false|true|Error string|
|Reason|string|false|true|Error reason string|
|Resolution|string|false|true|Resolution string|

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

