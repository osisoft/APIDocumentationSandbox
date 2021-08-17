---
uid: ""

---

# Client Failover Groups
The API controller for the failover groups.

## `List Group Configurations`

<a id="opIdClientFailoverGroups_List Group Configurations"></a>

GET /clientfailover/groups

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupConfiguration](#schemagroupconfiguration)[]|The result of the GET operation.|

<h4>Example response body</h4>

> 200 Response ([GroupConfiguration](#schemagroupconfiguration)[])

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "FailoverTimeout": "string"
  }
]
```

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post Group`

<a id="opIdClientFailoverGroups_Post Group"></a>

POST /clientfailover/groups

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>

<h4>Request Body</h4>

The failover group configuration being added.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The result from the POST operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Group Configuration`

<a id="opIdClientFailoverGroups_Get Group Configuration"></a>

GET /clientfailover/groups/{groupid}

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group configuration being retrieved.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The result of the GET operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Put Group`

<a id="opIdClientFailoverGroups_Put Group"></a>

PUT /clientfailover/groups/{groupid}

<h3>Request</h3>

```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group being updated.<br/><br/>

<h4>Request Body</h4>

The configuration of the failover group being updated.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The result of the PUT operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Delete Group`

<a id="opIdClientFailoverGroups_Delete Group"></a>

DELETE /clientfailover/groups/{groupid}

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group being deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The result of the DELETE operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `List Client Sessions`

<a id="opIdClientFailoverGroups_List Client Sessions"></a>

GET /clientfailover/groups/{groupid}/clientSessions

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientSessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSession](#schemaclientsession)[]|The response from the GET operation.|

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
      "HeartbeatTime": "2019-08-24T14:15:22Z",
      "LastDataProcessedTime": "2019-08-24T14:15:22Z"
    }
  }
]
```

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post Client Session`

<a id="opIdClientFailoverGroups_Post Client Session"></a>

POST /clientfailover/groups/{groupid}/clientsessions

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
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
    "HeartbeatTime": "2019-08-24T14:15:22Z",
    "LastDataProcessedTime": "2019-08-24T14:15:22Z"
  }
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The result from the POST operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Get Client Session`

<a id="opIdClientFailoverGroups_Get Client Session"></a>

GET /clientfailover/groups/{groupid}/clientSessions/{sessionid}

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientSessions/{sessionid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group.<br/><br/>`string sessionid`
<br/>The Id of the client session.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The response from the GET operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Put Client Session`

<a id="opIdClientFailoverGroups_Put Client Session"></a>

PUT /clientfailover/groups/{groupId}/clientsessions/{sessionId}

<h3>Request</h3>

```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions/{sessionid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group.<br/><br/>`string sessionid`
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
    "HeartbeatTime": "2019-08-24T14:15:22Z",
    "LastDataProcessedTime": "2019-08-24T14:15:22Z"
  }
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The response from the PUT operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Delete Client Session`

<a id="opIdClientFailoverGroups_Delete Client Session"></a>

DELETE /clientfailover/groups/{groupid}/clientsessions/{sessionId}

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions/{sessionid}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group having its session deleted<br/><br/>`string sessionid`
<br/>The Id of the session being deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|The result of the DELETE operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---

## `Post Heartbeat Message`

<a id="opIdClientFailoverGroups_Post Heartbeat Message"></a>

POST /clientfailover/groups/{groupid}/clientsessions/{sessionId}/heartbeat

<h3>Request</h3>

```text 
POST /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupid}/clientsessions/{sessionid}/heartbeat
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupid`
<br/>The Id of the failover group having its heartbeat posted.<br/><br/>`string sessionid`
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
|200|Inline|The result from the POST operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### GroupConfiguration

<a id="schemagroupconfiguration"></a>
<a id="schema_GroupConfiguration"></a>
<a id="tocSgroupconfiguration"></a>
<a id="tocsgroupconfiguration"></a>

The configuration of a failover group.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets the Id of the failover group configuration.|
|Name|string|false|true|Gets or sets the name of the failover group configuration.|
|Description|string|false|true|Gets or sets the description of the failover group configuration.|
|FailoverTimeout|time-span|false|false|Gets or sets the timeout of the failover group configuration in milliseconds.|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}

```

---

### ClientSession

<a id="schemaclientsession"></a>
<a id="schema_ClientSession"></a>
<a id="tocSclientsession"></a>
<a id="tocsclientsession"></a>

A failover group client session.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|Gets or sets the Id of a failover group client session.|
|Name|string|false|true|Gets or sets the name of a failover group client session.|
|Role|[ClientRole](#schemaclientrole)|false|false|None|
|Heartbeat|[IFailoverHeartbeat](#schemaifailoverheartbeat)|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Role": 0,
  "Heartbeat": {
    "FailoverStatus": 0,
    "HeartbeatTime": "2019-08-24T14:15:22Z",
    "LastDataProcessedTime": "2019-08-24T14:15:22Z"
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
|HeartbeatTime|date-time|false|false|None|
|LastDataProcessedTime|date-time|false|true|None|

```json
{
  "FailoverStatus": 0,
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}

```

---

### FailoverResponse

<a id="schemafailoverresponse"></a>
<a id="schema_FailoverResponse"></a>
<a id="tocSfailoverresponse"></a>
<a id="tocsfailoverresponse"></a>

The response of the failover of a failover group.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Role|[ClientRole](#schemaclientrole)|false|false|Gets or sets the client role of the failover group response.|
|LastDataProcessedTime|date-time|false|true|Gets or sets last data processed time in a failover group heartbeat.|

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

The heartbeat status of a failover group.

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HeartbeatTime|date-time|false|false|Gets or sets the last heartbeat time in a failover group heartbeat.|
|LastDataProcessedTime|date-time|false|true|Gets or sets last data processed time in a failover group heartbeat.|
|FailoverStatus|float|false|false|Gets or sets the failover status of a failover group heartbeat|

```json
{
  "HeartbeatTime": "2019-08-24T14:15:22Z",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z",
  "FailoverStatus": 0
}

```

---

