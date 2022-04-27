---
uid: ""

---

# Client Sessions
API for Client Sessions.

## `List Client Sessions`

<a id="opIdClientSessions_List Client Sessions"></a>

Returns the list of client sessions belonging to the specified group.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)[]|A list of client sessions.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified identifier was not found.|

<h4>Example response body</h4>

> 200 Response ([ClientSession](#schemaclientsession)[])

```json
[
  {
    "Id": "string",
    "AccessControl": {
      "RoleTrusteeAccessControlEntries": [
        {
          "Trustee": {
            "Type": 1,
            "ObjectId": "string",
            "TenantId": "string"
          },
          "AccessType": 0,
          "AccessRights": 0
        }
      ]
    },
    "Owner": {
      "Type": 1,
      "ObjectId": "string",
      "TenantId": "string"
    },
    "Name": "string",
    "Role": 0,
    "Heartbeat": {
      "FailoverStatus": 0,
      "LastDataProcessedTime": "2019-08-24T14:15:22Z",
      "HeartbeatTime": "2019-08-24T14:15:22Z"
    },
    "HeartbeatPosted": true,
    "Mode": true,
    "ModeExpirationTime": "2019-08-24T14:15:22Z"
  }
]
```

---

## `Post Client Session`

<a id="opIdClientSessions_Post Client Session"></a>

Creates a client session from specified session configuration.

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h4>Request Body</h4>

The client session being created.<br/>

```json
{
  "Id": "string",
  "Name": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSession](#schemaclientsession)|The client session was created.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified identifier was not found.|
|409|[ErrorResponse](#schemaerrorresponse)|A client session with the specified configuration already exists.|

<h4>Example response body</h4>

> 201 Response ([ClientSession](#schemaclientsession))

```json
{
  "Id": "string",
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": {
          "Type": 1,
          "ObjectId": "string",
          "TenantId": "string"
        },
        "AccessType": 0,
        "AccessRights": 0
      }
    ]
  },
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  },
  "HeartbeatPosted": true,
  "Mode": true,
  "ModeExpirationTime": "2019-08-24T14:15:22Z"
}
```

---

## `Get Client Session`

<a id="opIdClientSessions_Get Client Session"></a>

Gets a client session by identifier.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>`string sessionId`
<br/>The identifier of the client session.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)|Client session with the specified identifier.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group or client session with the specified identifier was not found.|

<h4>Example response body</h4>

> 200 Response ([ClientSession](#schemaclientsession))

```json
{
  "Id": "string",
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": {
          "Type": 1,
          "ObjectId": "string",
          "TenantId": "string"
        },
        "AccessType": 0,
        "AccessRights": 0
      }
    ]
  },
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  },
  "HeartbeatPosted": true,
  "Mode": true,
  "ModeExpirationTime": "2019-08-24T14:15:22Z"
}
```

---

## `Delete Client Session`

<a id="opIdClientSessions_Delete Client Session"></a>

Deletes a client session by identifier.

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>`string sessionId`
<br/>The identifier of the client session.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The client session was deleted.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group or client session with the specified identifier was not found.|

---

## `Post Heartbeat Message`

<a id="opIdClientSessions_Post Heartbeat Message"></a>

Posts a heartbeat to the client session.

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}/heartbeat
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>`string sessionId`
<br/>The identifier of the client session.<br/><br/>

<h4>Request Body</h4>

The heartbeat of the client session.<br/>

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
|200|[FailoverResponse](#schemafailoverresponse)|The failover response.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group or client session with the specified identifier was not found.|
|429|[ErrorResponse](#schemaerrorresponse)|Too many requests.|

<h4>Example response body</h4>

> 200 Response ([FailoverResponse](#schemafailoverresponse))

```json
{
  "Role": 0,
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}
```

---

## `Post Maintenance Mode`

<a id="opIdClientSessions_Post Maintenance Mode"></a>

Posts maintenance mode to the client session.

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/clientsessions/{sessionId}/mode
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>`string sessionId`
<br/>The identifier of the client session.<br/><br/>

<h4>Request Body</h4>

The maintenance mode detail configuration for the client session MaintenanceModeConfiguration. when modeDetail is not specified, default is to set maintenance mode to true with expireAfter TimeSpan of one hour. Optional "mode" of either true or false. When not specified, default is true. "mode" of true puts session under maintenance and false puts session out of maintenance. Optional "expireafter" of timespan in the format of "hh:mm:ss". "expireafter" value is only applicable when "mode" is true. When not specified, default value for "expireafter" is "01:00:00".<br/>

```json
{
  "Mode": true,
  "ExpireAfter": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[MaintenanceModeResponse](#schemamaintenancemoderesponse)|The failover response.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group or client session with the specified identifier was not found.|

<h4>Example response body</h4>

> 200 Response ([MaintenanceModeResponse](#schemamaintenancemoderesponse))

```json
{
  "Mode": true,
  "ModeExpirationTime": "2019-08-24T14:15:22Z"
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
|AccessControl|[AccessControlList](#schemaaccesscontrollist)|false|true|None|
|Owner|[Trustee](#schematrustee)|false|true|None|
|Name|string|false|true|None|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|Heartbeat|[IFailoverHeartbeat](#schemaifailoverheartbeat)|false|true|None|
|HeartbeatPosted|boolean|false|false|Whether a heartbeat has been Posted from the session.|
|Mode|boolean|false|false|Whether a Client Session is in Maintenance mode. False: Client is not in Maintenance and its Role is automatically calculated by Failover Engine. (Default). True: Client is in Maintenance and its Role is not calculated by Failover Engine.|
|ModeExpirationTime|date-time|false|true|When the Maintenance mode expires.|

```json
{
  "Id": "string",
  "AccessControl": {
    "RoleTrusteeAccessControlEntries": [
      {
        "Trustee": {
          "Type": 1,
          "ObjectId": "string",
          "TenantId": "string"
        },
        "AccessType": 0,
        "AccessRights": 0
      }
    ]
  },
  "Owner": {
    "Type": 1,
    "ObjectId": "string",
    "TenantId": "string"
  },
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "LastDataProcessedTime": "2019-08-24T14:15:22Z",
    "HeartbeatTime": "2019-08-24T14:15:22Z"
  },
  "HeartbeatPosted": true,
  "Mode": true,
  "ModeExpirationTime": "2019-08-24T14:15:22Z"
}

```

---

### AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": 1,
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

### AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

<h4>Properties</h4>

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

### Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

<h4>Properties</h4>

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

### TrusteeType

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

---

### AccessType

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

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
|AdditionalParameters|object|false|true|Additional parameters to add to the response.|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "AdditionalParameters": {
    "property1": null,
    "property2": null
  },
  "property1": null,
  "property2": null
}

```

---

### ClientSessionConfiguration

<a id="schemaclientsessionconfiguration"></a>
<a id="schema_ClientSessionConfiguration"></a>
<a id="tocSclientsessionconfiguration"></a>
<a id="tocsclientsessionconfiguration"></a>

Configuration for creating a new client session.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Unique client session identifier|
|Name|string|false|true|Friendly name of client session.|

```json
{
  "Id": "string",
  "Name": "string"
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

### MaintenanceModeResponse

<a id="schemamaintenancemoderesponse"></a>
<a id="schema_MaintenanceModeResponse"></a>
<a id="tocSmaintenancemoderesponse"></a>
<a id="tocsmaintenancemoderesponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Mode|boolean|false|false|Maintenance mode.|
|ModeExpirationTime|date-time|false|true|Maintenance mode expiration time.|

```json
{
  "Mode": true,
  "ModeExpirationTime": "2019-08-24T14:15:22Z"
}

```

---

### MaintenanceModeConfiguration

<a id="schemamaintenancemodeconfiguration"></a>
<a id="schema_MaintenanceModeConfiguration"></a>
<a id="tocSmaintenancemodeconfiguration"></a>
<a id="tocsmaintenancemodeconfiguration"></a>

MaintenanceModeConfiguration.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Mode|boolean|false|false|Maintenance mode.|
|ExpireAfter|time-span|false|false|Maintenance mode expires after this TimeSpan elapses.|

```json
{
  "Mode": true,
  "ExpireAfter": "string"
}

```

---

