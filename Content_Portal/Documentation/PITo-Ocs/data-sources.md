---
title: PITo-Ocs/data-sources v20210310.4
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.5

---

<h1 id="pito-ocs-data-sources-data-sources">Data Sources</h1>

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

	

---
## List Data Sources

<a id="opIdDataSources_List Data Sources"></a>

Get all `DataSourceDto` objects associated with the specified Namespace.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources
```

<h3 id="datasources_list-data-sources-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Namespace that the DataSource collection belongs to.<br/><br/>

<h3 id="datasources_list-data-sources-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)[]|The requested collection of `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Create Data Source

<a id="opIdDataSources_Create Data Source"></a>

Creates a new DataSource.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources
```

### Request Body

The DataSourceCreateUpdateDto to use when creating the DataSource.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3 id="datasources_create-data-source-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>

<h3 id="datasources_create-data-source-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[DataSourceDto](#schemadatasourcedto)|A `DataSourceDto` object corresponding to the newly created DataSource|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TenantId": "string",
  "OcsNamespace": "string",
  "Agent": {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": null,
      "Name": null,
      "Version": null,
      "AFServerId": null,
      "AFName": null,
      "AFVersion": null,
      "LastCommunicationTime": null,
      "Transfers": null
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true
  }
}
```

---
## Get Data Source

<a id="opIdDataSources_Get Data Source"></a>

Get the `DataSourceDto` object specified by the `dataSourceId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

<h3 id="datasources_get-data-source-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the requested DataSource.<br/><br/>

<h3 id="datasources_get-data-source-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|The requested `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TenantId": "string",
  "OcsNamespace": "string",
  "Agent": {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": null,
      "Name": null,
      "Version": null,
      "AFServerId": null,
      "AFName": null,
      "AFVersion": null,
      "LastCommunicationTime": null,
      "Transfers": null
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true
  }
}
```

---
## Update Data Source

<a id="opIdDataSources_Update Data Source"></a>

Replace an existing DataSource specified by the `dataSourceId`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

### Request Body

The new property values that will be set on the DataSource.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3 id="datasources_update-data-source-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource to replace.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_update-data-source-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|A `DataSourceDto` representing the replacement DataSource object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TenantId": "string",
  "OcsNamespace": "string",
  "Agent": {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": null,
      "Name": null,
      "Version": null,
      "AFServerId": null,
      "AFName": null,
      "AFVersion": null,
      "LastCommunicationTime": null,
      "Transfers": null
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true
  }
}
```

---
## Delete Data Source

<a id="opIdDataSources_Delete Data Source"></a>

Delete a DataSource specified by the `dataSourceId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

<h3 id="datasources_delete-data-source-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource to be deleted.<br/><br/>

<h3 id="datasources_delete-data-source-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The DataSource was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Get Agent

<a id="opIdDataSources_Get Agent"></a>

Get the `DataSourceDto` object specified by the `dataSourceId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{dataSourceId}/agents/{agentId}
```

<h3 id="datasources_get-agent-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the requested DataSource.<br/><br/>`string agentId`<br/>The Id of the requested Agent.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_get-agent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|The requested `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TenantId": "string",
  "OcsNamespace": "string",
  "Agent": {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": null,
      "Name": null,
      "Version": null,
      "AFServerId": null,
      "AFName": null,
      "AFVersion": null,
      "LastCommunicationTime": null,
      "Transfers": null
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true
  }
}
```

---
## Delete Agent

<a id="opIdDataSources_Delete Agent"></a>

Delete the Agent specified by `agentId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}
```

<h3 id="datasources_delete-agent-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent to be deleted.<br/><br/>

<h3 id="datasources_delete-agent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Agent was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## List Capabilities For Agent

<a id="opIdDataSources_List Capabilities For Agent"></a>

Get all `Capability` objects associated with the Agent specified by `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/capabilities
```

<h3 id="datasources_list-capabilities-for-agent-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the Capability collection belongs to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-capabilities-for-agent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Capability](#schemacapability)[]|200: A collection of `Capability` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## List PI Point Queries

<a id="opIdDataSources_List PI Point Queries"></a>

Get all `PIPointQueryDto` objects associated with the Agent specified by `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries
```

<h3 id="datasources_list-pi-point-queries-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the PIPointQuery collection belongs to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-pi-point-queries-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryDto](#schemapipointquerydto)[]|A collection of `PIPointQueryDto` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Create PI Point Query

<a id="opIdDataSources_Create PI Point Query"></a>

Creates a new PIPointQuery.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries
```

### Request Body

The PIPointQuery to create.<br/>

```json
{
  "PointNameMask": "string",
  "PointSourceMask": "string"
}
```

<h3 id="datasources_create-pi-point-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h3 id="datasources_create-pi-point-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[PIPointQueryDto](#schemapipointquerydto)|A `PIPointQueryDto` representing the newly created PIPointQuery.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}
```

---
## Get PI Point Query

<a id="opIdDataSources_Get PI Point Query"></a>

Get `PIPointQueryDto` object specified by `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}
```

<h3 id="datasources_get-pi-point-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the Query collection belongs to.<br/><br/>`string piPointQueryId`<br/>The Id of the query.<br/><br/>

<h3 id="datasources_get-pi-point-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryDto](#schemapipointquerydto)|A `PIPointQueryDto` object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}
```

---
## Delete PI Point Query

<a id="opIdDataSources_Delete PI Point Query"></a>

Delete a PIPointQuery specified by the `piPointQueryId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}
```

<h3 id="datasources_delete-pi-point-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string piPointQueryId`<br/>The Id of the PIPointQuery" to be deleted.<br/><br/>

<h3 id="datasources_delete-pi-point-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The PIPointQuery was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Get PI Point Query Result

<a id="opIdDataSources_Get PI Point Query Result"></a>

Get the `PIPointQueryResultDto` associated with the query specified by `piPointQueryId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}/result
```

<h3 id="datasources_get-pi-point-query-result-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent associated with the resource.<br/><br/>`string piPointQueryId`<br/>The Id of the PIPointQuery.<br/><br/>

<h3 id="datasources_get-pi-point-query-result-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryResultDto](#schemapipointqueryresultdto)|The requested `PIPointQueryResultDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "ResultPIPointsAttributes": [
    {
      "PointId": 0,
      "Name": "string",
      "PointSource": "string",
      "Description": "string",
      "EngineeringUnits": "string"
    }
  ]
}
```

---
## Update PI System

<a id="opIdDataSources_Update PI System"></a>

Update an existing PiSystem.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/pisystems
```

### Request Body

The PiSystem properties to update.<br/>

```json
{
  "ServerId": "string",
  "Name": "string",
  "Version": "string",
  "AFServerId": "string",
  "AFName": "string",
  "AFVersion": "string",
  "LastCommunicationTime": "2019-08-24T14:15:22Z",
  "Transfers": [
    {
      "Id": "string",
      "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
      "Description": "string",
      "Status": 0,
      "LatestStreamingRead": "2019-08-24T14:15:22Z",
      "OnPremTransferStatus": 0,
      "PIPointCount": 0,
      "Metrics": {},
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ]
}
```

<h3 id="datasources_update-pi-system-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_update-pi-system-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PISystemDto](#schemapisystemdto)|A `PISystemDto` object representing the PiSystem that was updated.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "ServerId": "string",
  "Name": "string",
  "Version": "string",
  "AFServerId": "string",
  "AFName": "string",
  "AFVersion": "string",
  "LastCommunicationTime": "2019-08-24T14:15:22Z",
  "Transfers": [
    {
      "Id": "string",
      "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
      "Description": "string",
      "Status": 0,
      "LatestStreamingRead": "2019-08-24T14:15:22Z",
      "OnPremTransferStatus": 0,
      "PIPointCount": 0,
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ]
}
```

---
## List PI Systems

<a id="opIdDataSources_List PI Systems"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems
```

<h3 id="datasources_list-pi-systems-parameters">Parameters</h3>

`string dataSourceId`<br/><br/>`string agentId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-pi-systems-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)[]|None|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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
## List PI System

<a id="opIdDataSources_List PI System"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/{piSystemId}
```

<h3 id="datasources_list-pi-system-parameters">Parameters</h3>

`string dataSourceId`<br/><br/>`string agentId`<br/><br/>`string piSystemId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-pi-system-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)[]|None|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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
## Delete PI System

<a id="opIdDataSources_Delete PI System"></a>

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/{piSystemName}
```

<h3 id="datasources_delete-pi-system-parameters">Parameters</h3>

`string dataSourceId`<br/><br/>`string agentId`<br/><br/>`string piSystemName`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_delete-pi-system-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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
## Delete PI System By Server Id

<a id="opIdDataSources_Delete PI System By Server Id"></a>

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/PIServer/{piServerId}
```

<h3 id="datasources_delete-pi-system-by-server-id-parameters">Parameters</h3>

`string dataSourceId`<br/><br/>`string agentId`<br/><br/>`string piServerId`<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_delete-pi-system-by-server-id-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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
## List Queries

<a id="opIdDataSources_List Queries"></a>

Get all `QueryDto` objects associated with the Agent specified by `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries
```

<h3 id="datasources_list-queries-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the Query collection belongs to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-queries-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)[]|A collection of `QueryDto` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Create Query

<a id="opIdDataSources_Create Query"></a>

Creates a new Query.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries
```

### Request Body

The Query to create.<br/>

```json
{
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": null,
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Skip": 0,
  "Count": 0
}
```

<h3 id="datasources_create-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h3 id="datasources_create-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[QueryDto](#schemaquerydto)|A `QueryDto` object representing the newly created Query object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": {
      "Elements": null
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Status": 1,
  "Skip": 0,
  "Count": 0
}
```

---
## Get Query

<a id="opIdDataSources_Get Query"></a>

Get `QueryDto` object specified by `agentId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

<h3 id="datasources_get-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the Query collection belongs to.<br/><br/>`string queryId`<br/>The Id of the query.<br/><br/>

<h3 id="datasources_get-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)|A `QueryDto` object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": {
      "Elements": null
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Status": 1,
  "Skip": 0,
  "Count": 0
}
```

---
## Update Query Paging Info

<a id="opIdDataSources_Update Query Paging Info"></a>

Update a Query.

### Request
```text 
PATCH /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

### Request Body

The operations to update the Query.<br/>

```json
[
  {
    "op": 1,
    "path": "string",
    "value": null
  }
]
```

<h3 id="datasources_update-query-paging-info-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string queryId`<br/>The Id of the Query to update.<br/><br/>

<h3 id="datasources_update-query-paging-info-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)|The updated Query was accepted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": {
      "Elements": null
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Status": 1,
  "Skip": 0,
  "Count": 0
}
```

---
## Delete Query

<a id="opIdDataSources_Delete Query"></a>

Delete the Query specified by the `queryId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

<h3 id="datasources_delete-query-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string queryId`<br/>The Id of the Query to be deleted.<br/><br/>

<h3 id="datasources_delete-query-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Query was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Get Query Result

<a id="opIdDataSources_Get Query Result"></a>

Get the `QueryResultPageDto` associated with the query specified by `queryId`.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}/result
```

<h3 id="datasources_get-query-result-parameters">Parameters</h3>

`string tenantId`<br/>The Id of the OCS Tenant the resource belongs to.<br/><br/>`string namespaceId`<br/>The Id of the OCS Namespace the resource belongs to.<br/><br/>`string dataSourceId`<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent associated with the resource.<br/><br/>`string queryId`<br/>The Id of the query.<br/><br/>

<h3 id="datasources_get-query-result-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryResultPageDto](#schemaqueryresultpagedto)|The requested `QueryResultPageDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Results": [
    null
  ],
  "AdditionalInformation": {
    "property1": null,
    "property2": null
  }
}
```

---
## Get Transfers

<a id="opIdDataSources_Get Transfers"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers
```

<h3 id="datasources_get-transfers-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>`string dataSourceId`<br/><br/>`string agentId`<br/><br/>

<h3 id="datasources_get-transfers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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
## Create Transfer

<a id="opIdDataSources_Create Transfer"></a>

Creates a new Transfer.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers
```

### Request Body

Properties of the Transfer to create.<br/>

```json
{
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "Name": "string",
  "MetadataPrivacy": 0
}
```

<h3 id="datasources_create-transfer-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_create-transfer-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[TransferDto](#schematransferdto)|A `TransferDto` object representing to the newly created transfer.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 201 Response

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "PreviousHistoricChunkStart": "2019-08-24T14:15:22Z",
  "CurrentHistoricChunkStart": "2019-08-24T14:15:22Z",
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "HistoricalDataEndTime": "2019-08-24T14:15:22Z",
  "TransferredElementsCount": 0,
  "OnPremTransferStatus": 0,
  "DesiredStatus": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "PIPointsReferencedByAF": [
    0
  ],
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}
```

---
## Update Transfer

<a id="opIdDataSources_Update Transfer"></a>

Replace an existing Transfer specified by the `transferId`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}
```

### Request Body

The Transfer properties to update.<br/>

```json
{
  "Description": "string",
  "DesiredStatus": 0,
  "Name": "string",
  "MetadataPrivacy": 0
}
```

<h3 id="datasources_update-transfer-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`<br/>The Id of the Transfer" to be replaced.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_update-transfer-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)|A `TransferDto` object representing the Transfer that was replaced.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "PreviousHistoricChunkStart": "2019-08-24T14:15:22Z",
  "CurrentHistoricChunkStart": "2019-08-24T14:15:22Z",
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "HistoricalDataEndTime": "2019-08-24T14:15:22Z",
  "TransferredElementsCount": 0,
  "OnPremTransferStatus": 0,
  "DesiredStatus": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "PIPointsReferencedByAF": [
    0
  ],
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}
```

---
## Delete Transfer

<a id="opIdDataSources_Delete Transfer"></a>

Delete the Transfer specified by the `transferId`.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}
```

<h3 id="datasources_delete-transfer-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`<br/>The Id of the Transfer to be deleted.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_delete-transfer-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Transfer was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Set PI Points Referenced By AF

<a id="opIdDataSources_Set PI Points Referenced By AF"></a>

Assign PI points referenced by AF to the Transfer specified by `transferId`.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}/pointsFromAF
```

### Request Body

The updated set of points referenced by AF.<br/>

```json
[
  0
]
```

<h3 id="datasources_set-pi-points-referenced-by-af-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`<br/>The Id of the Transfer" to be updated.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_set-pi-points-referenced-by-af-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)|Success: returns a `TransferDto` object representing the updated Transfer.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 200 Response

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "PreviousHistoricChunkStart": "2019-08-24T14:15:22Z",
  "CurrentHistoricChunkStart": "2019-08-24T14:15:22Z",
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "HistoricalDataEndTime": "2019-08-24T14:15:22Z",
  "TransferredElementsCount": 0,
  "OnPremTransferStatus": 0,
  "DesiredStatus": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "PIPointsReferencedByAF": [
    0
  ],
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}
```

---
## List Transfer Stream Ids

<a id="opIdDataSources_List Transfer Stream Ids"></a>

Gets a List of Stream Ids associated with the transfer specified by `transferId`. This endpoint will return the Stream Ids before they are guaranteed to be created by the Agent.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}/streams
```

<h3 id="datasources_list-transfer-stream-ids-parameters">Parameters</h3>

`string dataSourceId`<br/>The Id of the dataSource associated with the resource.<br/><br/>`string agentId`<br/>The Id of the Agent the transfer belongs to.<br/><br/>`string transferId`<br/>The Id of the Transfer that the Stream Ids belong to.<br/><br/>`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_list-transfer-stream-ids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The requested string collection.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

### Example response body
> 500 Response

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
## Get All Namespace PI Systems

<a id="opIdDataSources_Get All Namespace PI Systems"></a>

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/PISystems
```

<h3 id="datasources_get-all-namespace-pi-systems-parameters">Parameters</h3>

`string tenantId`<br/><br/>`string namespaceId`<br/><br/>

<h3 id="datasources_get-all-namespace-pi-systems-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

### Example response body
> 500 Response

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

# Definitions

<h2 id="tocS_DataSourceDto">DataSourceDto</h2>

<a id="schemadatasourcedto"></a>
<a id="schema_DataSourceDto"></a>
<a id="tocSdatasourcedto"></a>
<a id="tocsdatasourcedto"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TenantId": "string",
  "OcsNamespace": "string",
  "Agent": {
    "Id": "string",
    "LastCommTime": "2019-08-24T14:15:22Z",
    "Version": "string",
    "Status": 0,
    "Description": "string",
    "HostName": "string",
    "PISystem": {
      "ServerId": null,
      "Name": null,
      "Version": null,
      "AFServerId": null,
      "AFName": null,
      "AFVersion": null,
      "LastCommunicationTime": null,
      "Transfers": null
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|TenantId|guid|false|false|None|
|OcsNamespace|string|false|true|None|
|Agent|[AgentDto](#schemaagentdto)|false|true|None|

<h2 id="tocS_AgentDto">AgentDto</h2>

<a id="schemaagentdto"></a>
<a id="schema_AgentDto"></a>
<a id="tocSagentdto"></a>
<a id="tocsagentdto"></a>

```json
{
  "Id": "string",
  "LastCommTime": "2019-08-24T14:15:22Z",
  "Version": "string",
  "Status": 0,
  "Description": "string",
  "HostName": "string",
  "PISystem": {
    "ServerId": "string",
    "Name": "string",
    "Version": "string",
    "AFServerId": "string",
    "AFName": "string",
    "AFVersion": "string",
    "LastCommunicationTime": "2019-08-24T14:15:22Z",
    "Transfers": [
      {
        "Id": "string",
        "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
        "Description": "string",
        "Status": "[",
        "LatestStreamingRead": "2019-08-24T14:15:22Z",
        "OnPremTransferStatus": "[",
        "PIPointCount": 0,
        "Metrics": null,
        "Name": "string",
        "MetadataPrivacy": "["
      }
    ]
  },
  "Namespace": "string",
  "Region": "string",
  "IsDeprecated": true
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|LastCommTime|date-time|false|false|None|
|Version|string|false|true|None|
|Status|[AgentStatus](#schemaagentstatus)|false|false|None|
|Description|string|false|true|None|
|HostName|string|false|true|None|
|PISystem|[PISystemDto](#schemapisystemdto)|false|true|None|
|Namespace|string|false|true|None|
|Region|string|false|true|None|
|IsDeprecated|boolean|false|false|None|

<h2 id="tocS_AgentStatus">AgentStatus</h2>

<a id="schemaagentstatus"></a>
<a id="schema_AgentStatus"></a>
<a id="tocSagentstatus"></a>
<a id="tocsagentstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Registering|0|
|Registered|1|
|Connected|2|
|Disconnected|3|
|Deleting|4|
|RegistrationFailed|5|
|DataSourceConnectionIssue|6|
|DataSourceSecurityIssue|7|
|Shutdown|8|
|MissingConfiguration|9|

<h2 id="tocS_PISystemDto">PISystemDto</h2>

<a id="schemapisystemdto"></a>
<a id="schema_PISystemDto"></a>
<a id="tocSpisystemdto"></a>
<a id="tocspisystemdto"></a>

```json
{
  "ServerId": "string",
  "Name": "string",
  "Version": "string",
  "AFServerId": "string",
  "AFName": "string",
  "AFVersion": "string",
  "LastCommunicationTime": "2019-08-24T14:15:22Z",
  "Transfers": [
    {
      "Id": "string",
      "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
      "Description": "string",
      "Status": 0,
      "LatestStreamingRead": "2019-08-24T14:15:22Z",
      "OnPremTransferStatus": 0,
      "PIPointCount": 0,
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ServerId|guid|false|false|None|
|Name|string|false|true|None|
|Version|string|false|true|None|
|AFServerId|guid|false|false|None|
|AFName|string|false|true|None|
|AFVersion|string|false|true|None|
|LastCommunicationTime|date-time|false|false|None|
|Transfers|[[TransferSummaryDto](#schematransfersummarydto)]|false|true|[Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability]|

<h2 id="tocS_TransferSummaryDto">TransferSummaryDto</h2>

<a id="schematransfersummarydto"></a>
<a id="schema_TransferSummaryDto"></a>
<a id="tocStransfersummarydto"></a>
<a id="tocstransfersummarydto"></a>

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "OnPremTransferStatus": 0,
  "PIPointCount": 0,
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}

```

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|HistoricalDataStartTime|date-time|false|false|None|
|Description|string|false|true|None|
|Status|[TransferStatus](#schematransferstatus)|false|false|None|
|LatestStreamingRead|date-time|false|false|None|
|OnPremTransferStatus|[TransferJobStatus](#schematransferjobstatus)|false|false|None|
|PIPointCount|int32|false|false|None|
|Metrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None|

<h2 id="tocS_TransferStatus">TransferStatus</h2>

<a id="schematransferstatus"></a>
<a id="schema_TransferStatus"></a>
<a id="tocStransferstatus"></a>
<a id="tocstransferstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|NotSet|0|
|Started|1|
|Stopped|2|

<h2 id="tocS_TransferJobStatus">TransferJobStatus</h2>

<a id="schematransferjobstatus"></a>
<a id="schema_TransferJobStatus"></a>
<a id="tocStransferjobstatus"></a>
<a id="tocstransferjobstatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Idle|0|
|SendingHistoricalData|1|
|SendingStreamingData|2|
|BackfillingStreamingGap|4|
|Done|8|
|UncategorizedError|16|
|StreamingErrorConsumerRemoved|32|
|StreamingErrorUpdateQueueOverflow|64|
|StreamingErrorSignupDropped|128|
|StreamingErrorProducerRemoved|256|
|StreamingErrorUnknown|512|
|PIPointTypeChangeDetected|1024|
|CreatingStreams|2048|

<h2 id="tocS_TransferMetricsDto">TransferMetricsDto</h2>

<a id="schematransfermetricsdto"></a>
<a id="schema_TransferMetricsDto"></a>
<a id="tocStransfermetricsdto"></a>
<a id="tocstransfermetricsdto"></a>

```json
{
  "StreamingEventCountPerSecond": 0,
  "HistoricalEventCountPerSecond": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamingEventCountPerSecond|float|false|false|None|
|HistoricalEventCountPerSecond|float|false|false|None|

<h2 id="tocS_DataPrivacy">DataPrivacy</h2>

<a id="schemadataprivacy"></a>
<a id="schema_DataPrivacy"></a>
<a id="tocSdataprivacy"></a>
<a id="tocsdataprivacy"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Undefined|0|
|Medium|1|
|None|2|
|High|3|
|Low|4|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

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

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|

<h2 id="tocS_TransferDto">TransferDto</h2>

<a id="schematransferdto"></a>
<a id="schema_TransferDto"></a>
<a id="tocStransferdto"></a>
<a id="tocstransferdto"></a>

```json
{
  "Id": "string",
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "Status": 0,
  "PreviousHistoricChunkStart": "2019-08-24T14:15:22Z",
  "CurrentHistoricChunkStart": "2019-08-24T14:15:22Z",
  "LatestStreamingRead": "2019-08-24T14:15:22Z",
  "HistoricalDataEndTime": "2019-08-24T14:15:22Z",
  "TransferredElementsCount": 0,
  "OnPremTransferStatus": 0,
  "DesiredStatus": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "PIPointsReferencedByAF": [
    0
  ],
  "Metrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}

```

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|HistoricalDataStartTime|date-time|false|false|None|
|Description|string|false|true|None|
|Status|[TransferStatus](#schematransferstatus)|false|false|None|
|PreviousHistoricChunkStart|date-time|false|false|None|
|CurrentHistoricChunkStart|date-time|false|false|None|
|LatestStreamingRead|date-time|false|false|None|
|HistoricalDataEndTime|date-time|false|false|None|
|TransferredElementsCount|int32|false|false|None|
|OnPremTransferStatus|[TransferJobStatus](#schematransferjobstatus)|false|false|None|
|DesiredStatus|[TransferStatus](#schematransferstatus)|false|false|None|
|PIPointIds|[integer]|false|true|None|
|AFElementIds|string[]|false|true|None|
|PIPointsReferencedByAF|[integer]|false|true|None|
|Metrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None|

<h2 id="tocS_QueryDto">QueryDto</h2>

<a id="schemaquerydto"></a>
<a id="schema_QueryDto"></a>
<a id="tocSquerydto"></a>
<a id="tocsquerydto"></a>

```json
{
  "Id": "string",
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": {
      "Elements": null
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Status": 1,
  "Skip": 0,
  "Count": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|QueryType|[QueryTypes](#schemaquerytypes)|false|false|None|
|PI|[QueryPIDto](#schemaquerypidto)|false|true|None|
|AF|[QueryAFDto](#schemaqueryafdto)|false|true|None|
|Status|[QueryStatus](#schemaquerystatus)|false|false|None|
|Skip|int32|false|false|None|
|Count|int32|false|false|None|

<h2 id="tocS_QueryTypes">QueryTypes</h2>

<a id="schemaquerytypes"></a>
<a id="schema_QueryTypes"></a>
<a id="tocSquerytypes"></a>
<a id="tocsquerytypes"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|None|0|
|PIPoint|1|
|AFDatabases|2|
|AFHierarchy|4|
|PIPointList|8|
|AFElementsFullPath|16|
|AFElementSearchByAttribute|32|
|AFAttributeLoad|64|
|AFElementReferencedPIPoints|128|

<h2 id="tocS_QueryPIDto">QueryPIDto</h2>

<a id="schemaquerypidto"></a>
<a id="schema_QueryPIDto"></a>
<a id="tocSquerypidto"></a>
<a id="tocsquerypidto"></a>

```json
{
  "PointMasks": {
    "property1": "string",
    "property2": "string"
  },
  "PointIds": [
    0
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointMasks|object|false|true|None|
|PointIds|[integer]|false|true|None|

<h2 id="tocS_QueryAFDto">QueryAFDto</h2>

<a id="schemaqueryafdto"></a>
<a id="schema_QueryAFDto"></a>
<a id="tocSqueryafdto"></a>
<a id="tocsqueryafdto"></a>

```json
{
  "HierarchyMasks": {
    "property1": "string",
    "property2": "string"
  },
  "ElementsFullPathMasks": {
    "Elements": [
      "string"
    ]
  },
  "ElementSearchByAttributeMasks": {
    "property1": "string",
    "property2": "string"
  },
  "ObjectIds": [
    "string"
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HierarchyMasks|object|false|true|None|
|ElementsFullPathMasks|[AFElementFullPathDto](#schemaafelementfullpathdto)|false|true|None|
|ElementSearchByAttributeMasks|object|false|true|None|
|ObjectIds|string[]|false|true|None|

<h2 id="tocS_QueryHierarchyMask">QueryHierarchyMask</h2>

<a id="schemaqueryhierarchymask"></a>
<a id="schema_QueryHierarchyMask"></a>
<a id="tocSqueryhierarchymask"></a>
<a id="tocsqueryhierarchymask"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|DatabaseId|1|
|Id|2|
|TreePath|3|
|Skip|4|
|Count|5|

<h2 id="tocS_AFElementFullPathDto">AFElementFullPathDto</h2>

<a id="schemaafelementfullpathdto"></a>
<a id="schema_AFElementFullPathDto"></a>
<a id="tocSafelementfullpathdto"></a>
<a id="tocsafelementfullpathdto"></a>

```json
{
  "Elements": [
    "string"
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Elements|string[]|false|true|None|

<h2 id="tocS_QueryElementSearchByAttributeMask">QueryElementSearchByAttributeMask</h2>

<a id="schemaqueryelementsearchbyattributemask"></a>
<a id="schema_QueryElementSearchByAttributeMask"></a>
<a id="tocSqueryelementsearchbyattributemask"></a>
<a id="tocsqueryelementsearchbyattributemask"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|DatabaseId|1|
|QueryString|2|
|AttributeName|3|

<h2 id="tocS_QueryStatus">QueryStatus</h2>

<a id="schemaquerystatus"></a>
<a id="schema_QueryStatus"></a>
<a id="tocSquerystatus"></a>
<a id="tocsquerystatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Accepted|1|
|Processing|2|
|Completed|3|
|NotSupportedByAgent|4|
|ProcessingFailedOnAgent|5|
|PartiallyCompleted|6|
|Interrupted|7|
|ProcessingOnAgent|8|
|Unknown|-1|

<h2 id="tocS_PIPointQueryDto">PIPointQueryDto</h2>

<a id="schemapipointquerydto"></a>
<a id="schema_PIPointQueryDto"></a>
<a id="tocSpipointquerydto"></a>
<a id="tocspipointquerydto"></a>

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|PointNameMask|string|false|true|None|
|PointSourceMask|string|false|true|None|
|Status|[PIPointQueryStatus](#schemapipointquerystatus)|false|false|None|

<h2 id="tocS_PIPointQueryStatus">PIPointQueryStatus</h2>

<a id="schemapipointquerystatus"></a>
<a id="schema_PIPointQueryStatus"></a>
<a id="tocSpipointquerystatus"></a>
<a id="tocspipointquerystatus"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Ready|0|
|Querying|1|
|Completed|2|
|NotSupportedByAgent|3|

<h2 id="tocS_QueryResultPageDto">QueryResultPageDto</h2>

<a id="schemaqueryresultpagedto"></a>
<a id="schema_QueryResultPageDto"></a>
<a id="tocSqueryresultpagedto"></a>
<a id="tocsqueryresultpagedto"></a>

```json
{
  "Results": [
    null
  ],
  "AdditionalInformation": {
    "property1": null,
    "property2": null
  }
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|[any]|false|true|None|
|AdditionalInformation|object|false|true|None|

<h2 id="tocS_PIPointQueryResultDto">PIPointQueryResultDto</h2>

<a id="schemapipointqueryresultdto"></a>
<a id="schema_PIPointQueryResultDto"></a>
<a id="tocSpipointqueryresultdto"></a>
<a id="tocspipointqueryresultdto"></a>

```json
{
  "ResultPIPointsAttributes": [
    {
      "PointId": 0,
      "Name": "string",
      "PointSource": "string",
      "Description": "string",
      "EngineeringUnits": "string"
    }
  ]
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ResultPIPointsAttributes|[[PIPointAttributesFromQueryResult](#schemapipointattributesfromqueryresult)]|false|true|None|

<h2 id="tocS_PIPointAttributesFromQueryResult">PIPointAttributesFromQueryResult</h2>

<a id="schemapipointattributesfromqueryresult"></a>
<a id="schema_PIPointAttributesFromQueryResult"></a>
<a id="tocSpipointattributesfromqueryresult"></a>
<a id="tocspipointattributesfromqueryresult"></a>

```json
{
  "PointId": 0,
  "Name": "string",
  "PointSource": "string",
  "Description": "string",
  "EngineeringUnits": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointId|int32|false|false|None|
|Name|string|false|true|None|
|PointSource|string|false|true|None|
|Description|string|false|true|None|
|EngineeringUnits|string|false|true|None|

<h2 id="tocS_Capability">Capability</h2>

<a id="schemacapability"></a>
<a id="schema_Capability"></a>
<a id="tocScapability"></a>
<a id="tocscapability"></a>

```json
{
  "id": "string",
  "ver": 0,
  "en": true
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|id|string|false|true|None|
|ver|int32|false|false|None|
|en|boolean|false|false|None|

<h2 id="tocS_DataSourceCreateUpdateDto">DataSourceCreateUpdateDto</h2>

<a id="schemadatasourcecreateupdatedto"></a>
<a id="schema_DataSourceCreateUpdateDto"></a>
<a id="tocSdatasourcecreateupdatedto"></a>
<a id="tocsdatasourcecreateupdatedto"></a>

```json
{
  "Name": "string",
  "Description": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|true|false|None|
|Description|string|false|true|None|

<h2 id="tocS_TransferCreateDto">TransferCreateDto</h2>

<a id="schematransfercreatedto"></a>
<a id="schema_TransferCreateDto"></a>
<a id="tocStransfercreatedto"></a>
<a id="tocstransfercreatedto"></a>

```json
{
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z",
  "Description": "string",
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "Name": "string",
  "MetadataPrivacy": 0
}

```

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HistoricalDataStartTime|date-time|true|false|None|
|Description|string|false|true|None|
|PIPointIds|[integer]|true|false|None|
|AFElementIds|string[]|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None|

<h2 id="tocS_QueryCreateUpdateDto">QueryCreateUpdateDto</h2>

<a id="schemaquerycreateupdatedto"></a>
<a id="schema_QueryCreateUpdateDto"></a>
<a id="tocSquerycreateupdatedto"></a>
<a id="tocsquerycreateupdatedto"></a>

```json
{
  "QueryType": 0,
  "PI": {
    "PointMasks": {
      "property1": "string",
      "property2": "string"
    },
    "PointIds": [
      0
    ]
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementsFullPathMasks": {
      "Elements": null
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Skip": 0,
  "Count": 0
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|QueryType|[QueryTypes](#schemaquerytypes)|false|true|None|
|PI|[QueryPIDto](#schemaquerypidto)|false|true|None|
|AF|[QueryAFDto](#schemaqueryafdto)|false|true|None|
|Skip|int32|false|false|None|
|Count|int32|false|false|None|

<h2 id="tocS_PatchDto">PatchDto</h2>

<a id="schemapatchdto"></a>
<a id="schema_PatchDto"></a>
<a id="tocSpatchdto"></a>
<a id="tocspatchdto"></a>

```json
{
  "op": 1,
  "path": "string",
  "value": null
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|op|[PatchOperation](#schemapatchoperation)|true|false|None|
|path|string|false|false|None|
|value|any|false|true|None|

<h2 id="tocS_PatchOperation">PatchOperation</h2>

<a id="schemapatchoperation"></a>
<a id="schema_PatchOperation"></a>
<a id="tocSpatchoperation"></a>
<a id="tocspatchoperation"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Add|1|
|Remove|2|
|Replace|3|
|Move|4|
|Copy|5|
|Test|6|

<h2 id="tocS_PIPointQueryCreateUpdateDto">PIPointQueryCreateUpdateDto</h2>

<a id="schemapipointquerycreateupdatedto"></a>
<a id="schema_PIPointQueryCreateUpdateDto"></a>
<a id="tocSpipointquerycreateupdatedto"></a>
<a id="tocspipointquerycreateupdatedto"></a>

```json
{
  "PointNameMask": "string",
  "PointSourceMask": "string"
}

```

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointNameMask|string|true|false|None|
|PointSourceMask|string|true|false|None|

<h2 id="tocS_TransferUpdateDto">TransferUpdateDto</h2>

<a id="schematransferupdatedto"></a>
<a id="schema_TransferUpdateDto"></a>
<a id="tocStransferupdatedto"></a>
<a id="tocstransferupdatedto"></a>

```json
{
  "Description": "string",
  "DesiredStatus": 0,
  "Name": "string",
  "MetadataPrivacy": 0
}

```

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/9344/Models-and-Backwards-Compatability

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Description|string|false|true|None|
|DesiredStatus|[TransferStatus](#schematransferstatus)|false|false|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None|

