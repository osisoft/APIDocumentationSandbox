---
uid: ""

---

# Client Failover
The API controller for Client Failover Application information.

## `Get Information`

<a id="opIdClientFailover_Get Information"></a>

GET /clientfailover

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
|200|Inline|The result of the GET operation.|

<h3>Authorization</h3>

Allowed for these roles: 
<ul>
<li>Tenant Member</li>
</ul>

---
## Definitions

### FailoverEndpointInfo

<a id="schemafailoverendpointinfo"></a>
<a id="schema_FailoverEndpointInfo"></a>
<a id="tocSfailoverendpointinfo"></a>
<a id="tocsfailoverendpointinfo"></a>

Information on the Ocs Client Failover application

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Version|string|false|true|Version of the application|

```json
{
  "Version": "string"
}

```

---

