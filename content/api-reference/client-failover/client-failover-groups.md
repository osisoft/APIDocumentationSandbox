---
uid: ""

---

# Client Failover Groups
API for Client Failover Groups.

## `List Group Configurations`

<a id="opIdClientFailoverGroups_List Group Configurations"></a>

Returns the list of failover groups.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups
?skip={skip}&count={count}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>
`[optional] integer skip`
<br/>The number of items to skip.<br/><br/>`[optional] integer count`
<br/>The number of items to return.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupConfiguration](#schemagroupconfiguration)[]|A list of failover groups.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|

<h4>Response Headers</h4>

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|Total number of failover groups.|

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

---

## `Post Group`

<a id="opIdClientFailoverGroups_Post Group"></a>

Creates a new failover group.

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
|201|[GroupConfiguration](#schemagroupconfiguration)|The failover group was created.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|409|[ErrorResponse](#schemaerrorresponse)|A failover group with the same ID already exists.|

<h4>Example response body</h4>

> 201 Response ([GroupConfiguration](#schemagroupconfiguration))

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}
```

---

## `Get Group Configuration`

<a id="opIdClientFailoverGroups_Get Group Configuration"></a>

Gets a failover group by ID.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The ID of the failover group configuration being retrieved.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupConfiguration](#schemagroupconfiguration)|Failover group with the specified ID.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified ID was not found.|

<h4>Example response body</h4>

> 200 Response ([GroupConfiguration](#schemagroupconfiguration))

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}
```

---

## `Put Group`

<a id="opIdClientFailoverGroups_Put Group"></a>

PUT /clientfailover/groups/{groupId}

<h3>Request</h3>

```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
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
|200|[GroupConfiguration](#schemagroupconfiguration)|The result of the PUT operation.|
|201|[GroupConfiguration](#schemagroupconfiguration)|The result of the PUT operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|[ErrorResponse](#schemaerrorresponse)|None|

<h4>Example response body</h4>

> 200 Response ([GroupConfiguration](#schemagroupconfiguration))

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
}
```

---

## `Delete Group`

<a id="opIdClientFailoverGroups_Delete Group"></a>

DELETE /clientfailover/groups/{groupId}

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group being deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The result of the DELETE operation.|
|400|[ErrorResponse](#schemaerrorresponse)|None|
|403|None|None|
|404|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Get Group Status`

<a id="opIdClientFailoverGroups_Get Group Status"></a>

GET /clientfailover/groups/{groupid}/status

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/status
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The Id of the failover group configuration being retrieved.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The result of the GET operation.|

---
## Definitions

### GroupConfiguration

<a id="schemagroupconfiguration"></a>
<a id="schema_GroupConfiguration"></a>
<a id="tocSgroupconfiguration"></a>
<a id="tocsgroupconfiguration"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|FailoverTimeout|time-span|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "FailoverTimeout": "string"
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

### IGroupStatus

<a id="schemaigroupstatus"></a>
<a id="schema_IGroupStatus"></a>
<a id="tocSigroupstatus"></a>
<a id="tocsigroupstatus"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Primary|string|false|true|None|
|PendingPrimary|string|false|true|None|
|LastDataProcessedTime|date-time|false|true|None|

```json
{
  "Primary": "string",
  "PendingPrimary": "string",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}

```

---

