---
uid: ""

---

# Client Failover Groups

## `List`

<a id="opIdClientFailoverGroups_List"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupSessions](#schemagroupsessions)[]|None|

#### Example response body
> 200 Response ([GroupSessions](#schemagroupsessions)[])

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "FailoverTimeout": "string",
    "Milliseconds": 0,
    "Sessions": {
      "property1": {
        "Id": "string",
        "Name": "string"
      },
      "property2": {
        "Id": "string",
        "Name": "string"
      }
    },
    "Clients": {
      "property1": {
        "SessionId": "string",
        "Role": 0,
        "Heartbeat": {
          "PercentHealthyStreams": null,
          "HeartbeatTime": null,
          "LastDataSendTime": null
        }
      },
      "property2": {
        "SessionId": "string",
        "Role": 0,
        "Heartbeat": {
          "PercentHealthyStreams": null,
          "HeartbeatTime": null,
          "LastDataSendTime": null
        }
      }
    }
  }
]
```

---

## `Post`

<a id="opIdClientFailoverGroups_Post"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string",
  "Milliseconds": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Get (groupid path)`

<a id="opIdClientFailoverGroups_Get (groupid path)"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

#### Parameters

`string groupid`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|None|

---

## `Put`

<a id="opIdClientFailoverGroups_Put"></a>

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

#### Parameters

`string groupid`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string",
  "Milliseconds": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Delete`

<a id="opIdClientFailoverGroups_Delete"></a>

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

#### Parameters

`string groupid`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Post Heartbeat Message`

<a id="opIdClientFailoverGroups_Post Heartbeat Message"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions/{sessionId}
```

#### Parameters

`string groupid`
<br/><br/>`string sessionId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "PercentHealthyStreams": 0,
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataSendTime": "2019-08-24T14:15:22Z"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|None|

---

## `Post Client Sessions`

<a id="opIdClientFailoverGroups_Post Client Sessions"></a>

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions
```

#### Parameters

`string groupid`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Request Body

<br/>

```json
{
  "Id": "string",
  "Name": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## `Delete (clientsessions path)`

<a id="opIdClientFailoverGroups_Delete (clientsessions path)"></a>

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions/{sessionid}
```

#### Parameters

`string groupid`
<br/><br/>`string sessionId`
<br/><br/>`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
## Definitions

### GroupSessions

<a id="schemagroupsessions"></a>
<a id="schema_GroupSessions"></a>
<a id="tocSgroupsessions"></a>
<a id="tocsgroupsessions"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|FailoverTimeout|time-span|false|false|None|
|Milliseconds|double|false|false|None|
|Sessions|object|false|true|None|
|Clients|object|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string",
  "Milliseconds": 0,
  "Sessions": {
    "property1": {
      "Id": "string",
      "Name": "string"
    },
    "property2": {
      "Id": "string",
      "Name": "string"
    }
  },
  "Clients": {
    "property1": {
      "SessionId": "string",
      "Role": 0,
      "Heartbeat": {
        "PercentHealthyStreams": 0,
        "HeartbeatTime": "2019-08-24T14:15:22Z",
        "LastDataSendTime": "2019-08-24T14:15:22Z"
      }
    },
    "property2": {
      "SessionId": "string",
      "Role": 0,
      "Heartbeat": {
        "PercentHealthyStreams": 0,
        "HeartbeatTime": "2019-08-24T14:15:22Z",
        "LastDataSendTime": "2019-08-24T14:15:22Z"
      }
    }
  }
}

```

---

### ClientSession

<a id="schemaclientsession"></a>
<a id="schema_ClientSession"></a>
<a id="tocSclientsession"></a>
<a id="tocsclientsession"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|

```json
{
  "Id": "string",
  "Name": "string"
}

```

---

### IClientStatus

<a id="schemaiclientstatus"></a>
<a id="schema_IClientStatus"></a>
<a id="tocSiclientstatus"></a>
<a id="tocsiclientstatus"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|SessionId|string|false|true|None|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|Heartbeat|[IFailoverHeartbeat](#schemaifailoverheartbeat)|false|true|None|

```json
{
  "SessionId": "string",
  "Role": 0,
  "Heartbeat": {
    "PercentHealthyStreams": 0,
    "HeartbeatTime": "2019-08-24T14:15:22Z",
    "LastDataSendTime": "2019-08-24T14:15:22Z"
  }
}

```

---

### ClientRole

<a id="schemaclientrole"></a>
<a id="schema_ClientRole"></a>
<a id="tocSclientrole"></a>
<a id="tocsclientrole"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Secondary|0|
|Primary|1|
|PendingPrimary|2|

---

### IFailoverHeartbeat

<a id="schemaifailoverheartbeat"></a>
<a id="schema_IFailoverHeartbeat"></a>
<a id="tocSifailoverheartbeat"></a>
<a id="tocsifailoverheartbeat"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PercentHealthyStreams|decimal|false|false|None|
|HeartbeatTime|date-time|false|false|None|
|LastDataSendTime|date-time|false|false|None|

```json
{
  "PercentHealthyStreams": 0,
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataSendTime": "2019-08-24T14:15:22Z"
}

```

---

### GroupConfiguration

<a id="schemagroupconfiguration"></a>
<a id="schema_GroupConfiguration"></a>
<a id="tocSgroupconfiguration"></a>
<a id="tocsgroupconfiguration"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|FailoverTimeout|time-span|false|false|None|
|Milliseconds|double|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string",
  "Milliseconds": 0
}

```

---

### FailoverResponse

<a id="schemafailoverresponse"></a>
<a id="schema_FailoverResponse"></a>
<a id="tocSfailoverresponse"></a>
<a id="tocsfailoverresponse"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|LastDataSendTime|date-time|false|false|None|

```json
{
  "Role": 0,
  "LastDataSendTime": "2019-08-24T14:15:22Z"
}

```

---

### FailoverHeartbeat

<a id="schemafailoverheartbeat"></a>
<a id="schema_FailoverHeartbeat"></a>
<a id="tocSfailoverheartbeat"></a>
<a id="tocsfailoverheartbeat"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PercentHealthyStreams|decimal|false|false|None|
|HeartbeatTime|date-time|false|false|None|
|LastDataSendTime|date-time|false|false|None|

```json
{
  "PercentHealthyStreams": 0,
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataSendTime": "2019-08-24T14:15:22Z"
}

```

---

