---
uid: ""

---

# Client Sessions
API for Client Sessions.

## `List Client Sessions`

<a id="opIdClientSessions_List Client Sessions"></a>

GET /clientfailover/groups/{groupId}/clientSessions

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)[]|The response from the GET operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 200 Response ([ClientSession](#schemaclientsession)[])

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Role": 0,
    "Heartbeat": {
      "FailoverStatus": 0,
      "LastDataProcessedTime": "2019-08-24T14:15:22Z",
      "HeartbeatTime": "2019-08-24T14:15:22Z"
    }
  }
]
```

---

## `Post Client Session`

<a id="opIdClientSessions_Post Client Session"></a>

POST /clientfailover/groups/{groupId}/clientsessions

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group having its client sessions posted.<br/><br/>

<h4>Request Body</h4>

The client session being posted.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSession](#schemaclientsession)|The result from the POST operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|
|409|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 201 Response ([ClientSession](#schemaclientsession))

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}
```

---

## `Get Client Session`

<a id="opIdClientSessions_Get Client Session"></a>

GET /clientfailover/groups/{groupId}/clientSessions/{sessionId}

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group.<br/><br/>`string sessionId`
<br/>The Id of the client session.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)|The response from the GET operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 200 Response ([ClientSession](#schemaclientsession))

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}
```

---

## `Put Client Session`

<a id="opIdClientSessions_Put Client Session"></a>

PUT /clientfailover/groups/{groupId}/clientsessions/{sessionId}

<h3>Request</h3>

```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group.<br/><br/>`string sessionId`
<br/>The Id of the client session.<br/><br/>

<h4>Request Body</h4>

The client session updates.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)|The response from the PUT operation.|
|201|[ClientSession](#schemaclientsession)|The response from the PUT operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 200 Response ([ClientSession](#schemaclientsession))

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}
```

---

## `Delete Client Session`

<a id="opIdClientSessions_Delete Client Session"></a>

DELETE /clientfailover/groups/{groupId}/clientsessions/{sessionId}

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group having its session deleted<br/><br/>`string sessionId`
<br/>The Id of the session being deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The result of the DELETE operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Post Heartbeat Message`

<a id="opIdClientSessions_Post Heartbeat Message"></a>

POST /clientfailover/groups/{groupId}/clientsessions/{sessionId}/heartbeat

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}/heartbeat
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group having its heartbeat posted.<br/><br/>`string sessionId`
<br/>The session Id of the failover group having its heartbeat posted.<br/><br/>

<h4>Request Body</h4>

The heartbeat of the failover group.<br/>

```json
{
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z",
  "FailoverStatus": 0
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[FailoverResponse](#schemafailoverresponse)|The result from the POST operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 200 Response ([FailoverResponse](#schemafailoverresponse))

```json
{
  "Role": 0,
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}
```

---
## Definitions

### ClientSession

<a id="schemaclientsession"></a>
<a id="schema_ClientSession"></a>
<a id="tocSclientsession"></a>
<a id="tocsclientsession"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|Heartbeat|[IFailoverHeartbeat](#schemaifailoverheartbeat)|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  }
}

```

---

### ClientRole

<a id="schemaclientrole"></a>
<a id="schema_ClientRole"></a>
<a id="tocSclientrole"></a>
<a id="tocsclientrole"></a>

<h4>Enumerated Values</h4>

|Property|Value|Description|
|---|---|---|
|Secondary|0||
|Primary|1||
|PendingPrimary|2||

---

### IFailoverHeartbeat

<a id="schemaifailoverheartbeat"></a>
<a id="schema_IFailoverHeartbeat"></a>
<a id="tocSifailoverheartbeat"></a>
<a id="tocsifailoverheartbeat"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|FailoverStatus|float|false|false|None|
|LastDataProcessedTime|date-time|false|true|None|
|HeartbeatTime|date-time|false|false|None|

```json
{
  "FailoverStatus": 0,
  "LastDataProcessedTime": "2019-08-24T14:15:22Z",
  "HeartbeatTime": "2019-08-24T14:15:22Z"
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

### FailoverResponse

<a id="schemafailoverresponse"></a>
<a id="schema_FailoverResponse"></a>
<a id="tocSfailoverresponse"></a>
<a id="tocsfailoverresponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|LastDataProcessedTime|date-time|false|true|None|

```json
{
  "Role": 0,
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}

```

---

### FailoverHeartbeat

<a id="schemafailoverheartbeat"></a>
<a id="schema_FailoverHeartbeat"></a>
<a id="tocSfailoverheartbeat"></a>
<a id="tocsfailoverheartbeat"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HeartbeatTime|date-time|false|false|None|
|LastDataProcessedTime|date-time|false|true|None|
|FailoverStatus|float|false|false|None|

```json
{
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z",
  "FailoverStatus": 0
}

```

---

