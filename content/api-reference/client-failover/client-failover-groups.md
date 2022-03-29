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
    "Description": "string",
    "FailoverTimeout": "string"
  }
]
```

---

## `Get Group Configuration`

<a id="opIdClientFailoverGroups_Get Group Configuration"></a>

Gets a failover group by identifier.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupConfiguration](#schemagroupconfiguration)|Failover group with the specified identifier.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified identifier was not found.|

<h4>Example response body</h4>

> 200 Response ([GroupConfiguration](#schemagroupconfiguration))

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
  "Description": "string",
  "FailoverTimeout": "string"
}
```

---

## `Put Group`

<a id="opIdClientFailoverGroups_Put Group"></a>

Creates or updates a failover group by identifier.

<h3>Request</h3>

```text 
PUT /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h4>Request Body</h4>

The configuration of the failover group being created or updated.<br/>

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
  "Description": "string",
  "FailoverTimeout": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[GroupConfiguration](#schemagroupconfiguration)|The failover group was updated.|
|201|[GroupConfiguration](#schemagroupconfiguration)|The failover group was created.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|

<h4>Example response body</h4>

> 200 Response ([GroupConfiguration](#schemagroupconfiguration))

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
  "Description": "string",
  "FailoverTimeout": "string"
}
```

---

## `Delete Group`

<a id="opIdClientFailoverGroups_Delete Group"></a>

Deletes a failover group by identifier.

<h3>Request</h3>

```text 
DELETE /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The failover group was deleted.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified identifier was not found.|

---

## `Get Group Status`

<a id="opIdClientFailoverGroups_Get Group Status"></a>

Gets the failover group status.

<h3>Request</h3>

```text 
GET /api/v1-preview/tenants/{tenantId}/namespaces/{namespaceId}/clientfailover/groups/{groupId}/status
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string groupId`
<br/>The identifier of the failover group.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IGroupStatus](#schemaigroupstatus)|The failover group status.|
|400|[ErrorResponse](#schemaerrorresponse)|Request is not valid. See the response body for additional details.|
|403|[ErrorResponse](#schemaerrorresponse)|Request is not authorized.|
|404|[ErrorResponse](#schemaerrorresponse)|A failover group with the specified identifier was not found.|

<h4>Example response body</h4>

> 200 Response ([IGroupStatus](#schemaigroupstatus))

```json
{
  "Primary": "string",
  "PendingPrimary": "string",
  "LastDataProcessedTime": "2019-08-24T14:15:22Z"
}
```

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
|AccessControl|[AccessControlList](#schemaaccesscontrollist)|false|true|None|
|Owner|[Trustee](#schematrustee)|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|FailoverTimeout|time-span|false|false|None|

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
  "Description": "string",
  "FailoverTimeout": "string"
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

