---
uid: ""

---

# Data Sources

## `List Data Sources`

<a id="opIdDataSources_List Data Sources"></a>

Get all `DataSourceDto` objects associated with the specified Namespace.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)[]|The requested collection of `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([DataSourceDto](#schemadatasourcedto)[])

```json
[
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
              "StreamingEventCountPerSecond": null,
              "HistoricalEventCountPerSecond": null,
              "SuccessfulCreations": null,
              "FailedCreations": null,
              "TotalPoints": null,
              "AssetsCreatedPerSecond": null,
              "AssetsProcessedCount": null,
              "TotalAssetsInTransfer": null
            },
            "Name": "string",
            "MetadataPrivacy": 0
          }
        ],
        "AFIndexProgress": 0,
        "ElementsIndexed": 0,
        "TotalElements": 0
      },
      "Namespace": "string",
      "Region": "string",
      "IsDeprecated": true,
      "TransferMetrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      }
    }
  }
]
```

---

## `Create Data Source`

<a id="opIdDataSources_Create Data Source"></a>

Creates a new DataSource.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>

<h4>Request Body</h4>

The DataSourceCreateUpdateDto to use when creating the DataSource.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[DataSourceDto](#schemadatasourcedto)|A `DataSourceDto` object corresponding to the newly created DataSource|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 201 Response ([DataSourceDto](#schemadatasourcedto))

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
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0
        }
      ],
      "AFIndexProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0
    }
  }
}
```

---

## `Get Data Source`

<a id="opIdDataSources_Get Data Source"></a>

Get the `DataSourceDto` object specified by the `dataSourceId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the requested DataSource.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|The requested `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([DataSourceDto](#schemadatasourcedto))

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
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0
        }
      ],
      "AFIndexProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0
    }
  }
}
```

---

## `Update Data Source`

<a id="opIdDataSources_Update Data Source"></a>

Replace an existing DataSource specified by the `dataSourceId`.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource to replace.<br/><br/>

<h4>Request Body</h4>

The new property values that will be set on the DataSource.<br/>

```json
{
  "Name": "string",
  "Description": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|A `DataSourceDto` representing the replacement DataSource object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([DataSourceDto](#schemadatasourcedto))

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
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0
        }
      ],
      "AFIndexProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0
    }
  }
}
```

---

## `Delete Data Source`

<a id="opIdDataSources_Delete Data Source"></a>

Delete a DataSource specified by the `dataSourceId`.

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource to be deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The DataSource was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `Get All Namespace PISystems`

<a id="opIdDataSources_Get All Namespace PISystems"></a>

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/PISystems
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Get Agent`

<a id="opIdDataSources_Get Agent"></a>

Get the `DataSourceDto` object specified by the `dataSourceId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the requested DataSource.<br/><br/>`string agentId`
<br/>The Id of the requested Agent.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataSourceDto](#schemadatasourcedto)|The requested `DataSourceDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([DataSourceDto](#schemadatasourcedto))

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
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0
        }
      ],
      "AFIndexProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0
    }
  }
}
```

---

## `Delete Agent`

<a id="opIdDataSources_Delete Agent"></a>

Delete the Agent specified by `agentId`.

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent to be deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Agent was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `List PISystems`

<a id="opIdDataSources_List PISystems"></a>

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>Data source identifier.<br/><br/>`string agentId`
<br/><span style="background-color:red;color:white">ERROR: Parameter "agentId" could not be found in external reference file</span><br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)[]|Success.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

<h4>Example response body</h4>

> 200 Response ([TransferDto](#schematransferdto)[])

```json
[
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
    "AssetsCreatedCount": 0,
    "AssetsUpdatedCount": 0,
    "AssetsFailedCount": 0,
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
    "Name": "string",
    "MetadataPrivacy": 0,
    "TransferRevisionNumber": 0,
    "LastEditDate": "2019-08-24T14:15:22Z",
    "LastEditBy": "string"
  }
]
```

---

## `Update PISystem`

<a id="opIdDataSources_Update PISystem"></a>

Update an existing PiSystem.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h4>Request Body</h4>

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
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ],
  "AFIndexProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PISystemDto](#schemapisystemdto)|A `PISystemDto` object representing the PiSystem that was updated.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([PISystemDto](#schemapisystemdto))

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
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ],
  "AFIndexProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0
}
```

---

## `List PISystem`

<a id="opIdDataSources_List PISystem"></a>

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/{piSystemId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>Data source identifier.<br/><br/>`string agentId`
<br/><span style="background-color:red;color:white">ERROR: Parameter "agentId" could not be found in external reference file</span><br/><br/>`string piSystemId`
<br/>PI System ID<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)[]|Success.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

<h4>Example response body</h4>

> 200 Response ([TransferDto](#schematransferdto)[])

```json
[
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
    "AssetsCreatedCount": 0,
    "AssetsUpdatedCount": 0,
    "AssetsFailedCount": 0,
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
    "Name": "string",
    "MetadataPrivacy": 0,
    "TransferRevisionNumber": 0,
    "LastEditDate": "2019-08-24T14:15:22Z",
    "LastEditBy": "string"
  }
]
```

---

## `Get Status`

<a id="opIdDataSources_Get Status"></a>

Retrieves the current overall status of an agent

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/status
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>Data source identifier.<br/><br/>`string agentId`
<br/><span style="background-color:red;color:white">ERROR: Parameter "agentId" could not be found in external reference file</span><br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AgentStatusDto](#schemaagentstatusdto)|Success.|
|404|None|Client or tenant not found.|

<h4>Example response body</h4>

> 200 Response ([AgentStatusDto](#schemaagentstatusdto))

```json
{
  "Agent": {
    "HealthStatus": 0,
    "InternalStatus": [
      "string"
    ]
  },
  "AssetFrameworkIndexing": {
    "HealthStatus": 0,
    "InternalStatus": [
      "string"
    ]
  },
  "Transfers": {
    "property1": {
      "HealthStatus": 0,
      "InternalStatus": [
        "string"
      ]
    },
    "property2": {
      "HealthStatus": 0,
      "InternalStatus": [
        "string"
      ]
    }
  }
}
```

---

## `Get Transfers`

<a id="opIdDataSources_Get Transfers"></a>

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>Data source identifier.<br/><br/>`string agentId`
<br/><span style="background-color:red;color:white">ERROR: Parameter "agentId" could not be found in external reference file</span><br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Create Transfer`

<a id="opIdDataSources_Create Transfer"></a>

Creates a new Transfer.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h4>Request Body</h4>

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

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[TransferDto](#schematransferdto)|A `TransferDto` object representing to the newly created transfer.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 201 Response ([TransferDto](#schematransferdto))

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
  "AssetsCreatedCount": 0,
  "AssetsUpdatedCount": 0,
  "AssetsFailedCount": 0,
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
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string"
}
```

---

## `List Transfer Stream Ids`

<a id="opIdDataSources_List Transfer Stream Ids"></a>

Gets a List of Stream Ids associated with the transfer specified by `transferId`. This endpoint will return the Stream Ids before they are guaranteed to be created by the Agent.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}/streams
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the dataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the transfer belongs to.<br/><br/>`string transferId`
<br/>The Id of the Transfer that the Stream Ids belong to.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|The requested string collection.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `List Queries`

<a id="opIdDataSources_List Queries"></a>

Get all `QueryDto` objects associated with the Agent specified by `agentId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the Query collection belongs to.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)[]|A collection of `QueryDto` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([QueryDto](#schemaquerydto)[])

```json
[
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
      ],
      "PointList": {
        "MetadataPrivacy": 0,
        "PointIds": [
          0
        ]
      }
    },
    "AF": {
      "HierarchyMasks": {
        "property1": "string",
        "property2": "string"
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
]
```

---

## `Create Query`

<a id="opIdDataSources_Create Query"></a>

Creates a new Query.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h4>Request Body</h4>

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Skip": 2147483647,
  "Count": 2147483647
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[QueryDto](#schemaquerydto)|A `QueryDto` object representing the newly created Query object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 201 Response ([QueryDto](#schemaquerydto))

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
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

## `Get Query`

<a id="opIdDataSources_Get Query"></a>

Get `QueryDto` object specified by `agentId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the Query collection belongs to.<br/><br/>`string queryId`
<br/>The Id of the query.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)|A `QueryDto` object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([QueryDto](#schemaquerydto))

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
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

## `Update Query Paging Info`

<a id="opIdDataSources_Update Query Paging Info"></a>

Update a Query.

<h3>Request</h3>

```text 
PATCH /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string queryId`
<br/>The Id of the Query to update.<br/><br/>

<h4>Request Body</h4>

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

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryDto](#schemaquerydto)|The updated Query was accepted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([QueryDto](#schemaquerydto))

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
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

## `Delete Query`

<a id="opIdDataSources_Delete Query"></a>

Delete the Query specified by the `queryId`.

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string queryId`
<br/>The Id of the Query to be deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Query was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `List PIPoint Queries`

<a id="opIdDataSources_List PIPoint Queries"></a>

Get all `PIPointQueryDto` objects associated with the Agent specified by `agentId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the PIPointQuery collection belongs to.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryDto](#schemapipointquerydto)[]|A collection of `PIPointQueryDto` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([PIPointQueryDto](#schemapipointquerydto)[])

```json
[
  {
    "Id": "string",
    "PointNameMask": "string",
    "PointSourceMask": "string",
    "Status": 0
  }
]
```

---

## `Create PIPoint Query`

<a id="opIdDataSources_Create PIPoint Query"></a>

Creates a new PIPointQuery.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h4>Request Body</h4>

The PIPointQuery to create.<br/>

```json
{
  "PointNameMask": "string",
  "PointSourceMask": "string"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[PIPointQueryDto](#schemapipointquerydto)|A `PIPointQueryDto` representing the newly created PIPointQuery.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 201 Response ([PIPointQueryDto](#schemapipointquerydto))

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}
```

---

## `Get PIPoint Query`

<a id="opIdDataSources_Get PIPoint Query"></a>

Get `PIPointQueryDto` object specified by `agentId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the Query collection belongs to.<br/><br/>`string piPointQueryId`
<br/>The Id of the query.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryDto](#schemapipointquerydto)|A `PIPointQueryDto` object.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([PIPointQueryDto](#schemapipointquerydto))

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}
```

---

## `Delete PIPoint Query`

<a id="opIdDataSources_Delete PIPoint Query"></a>

Delete a PIPointQuery specified by the `piPointQueryId`.

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string piPointQueryId`
<br/>The Id of the PIPointQuery" to be deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The PIPointQuery was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `Get Query Result`

<a id="opIdDataSources_Get Query Result"></a>

Get the `QueryResultPageDto` associated with the query specified by `queryId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}/result
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent associated with the resource.<br/><br/>`string queryId`
<br/>The Id of the query.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryResultPageDto](#schemaqueryresultpagedto)|The requested `QueryResultPageDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([QueryResultPageDto](#schemaqueryresultpagedto))

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

## `Get Query Status`

<a id="opIdDataSources_Get Query Status"></a>

Get the `QueryStatusDto` associated with the query specified by `queryId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/queries/{queryId}/status
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent associated with the resource.<br/><br/>`string queryId`
<br/>The Id of the query.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[QueryResultPageDto](#schemaqueryresultpagedto)|The requested `QueryStatusDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([QueryResultPageDto](#schemaqueryresultpagedto))

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

## `Get PIPoint Query Result`

<a id="opIdDataSources_Get PIPoint Query Result"></a>

Get the `PIPointQueryResultDto` associated with the query specified by `piPointQueryId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/piPointQueries/{piPointQueryId}/result
```

<h4>Parameters</h4>

`string tenantId`
<br/>Tenant identifier.<br/><br/>`string namespaceId`
<br/>Namespace identifier.<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent associated with the resource.<br/><br/>`string piPointQueryId`
<br/>The Id of the PIPointQuery.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PIPointQueryResultDto](#schemapipointqueryresultdto)|The requested `PIPointQueryResultDto`.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([PIPointQueryResultDto](#schemapipointqueryresultdto))

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

## `List Capabilities For Agent`

<a id="opIdDataSources_List Capabilities For Agent"></a>

Get all `Capability` objects associated with the Agent specified by `agentId`.

<h3>Request</h3>

```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/capabilities
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource associated with the resource.<br/><br/>`string agentId`
<br/>The Id of the Agent the Capability collection belongs to.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Capability](#schemacapability)[]|200: A collection of `Capability` objects.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([Capability](#schemacapability)[])

```json
[
  {
    "id": "string",
    "ver": 0,
    "en": true
  }
]
```

---

## `Update Transfer`

<a id="opIdDataSources_Update Transfer"></a>

Update Transfer specified by the `transferId`.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`
<br/>The Id of the Transfer" to be replaced.<br/><br/>

<h4>Request Body</h4>

The Transfer properties to update.<br/>

```json
{
  "Description": "string",
  "DesiredStatus": 0,
  "Name": "string",
  "MetadataPrivacy": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z"
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)|A `TransferDto` object representing the Transfer that was replaced.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([TransferDto](#schematransferdto))

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
  "AssetsCreatedCount": 0,
  "AssetsUpdatedCount": 0,
  "AssetsFailedCount": 0,
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
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string"
}
```

---

## `Delete Transfer`

<a id="opIdDataSources_Delete Transfer"></a>

Delete the Transfer specified by the `transferId`.

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`
<br/>The Id of the Transfer to be deleted.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The Transfer was deleted.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---

## `Update Transfer Status`

<a id="opIdDataSources_Update Transfer Status"></a>

Update desired status of the `transferId`.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}/status
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`
<br/>The Id of the Transfer" to be replaced.<br/><br/>

<h4>Request Body</h4>

The Transfer status to be changed to.<br/>

```json
{
  "DesiredStatus": 0
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)|A `TransferDto` object representing the Transfer that was updated.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([TransferDto](#schematransferdto))

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
  "AssetsCreatedCount": 0,
  "AssetsUpdatedCount": 0,
  "AssetsFailedCount": 0,
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
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string"
}
```

---

## `Update AF Index Progress`

<a id="opIdDataSources_Update AF Index Progress"></a>

Update an existing AF Index Progress information for the PISystem.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/indexprogress
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h4>Request Body</h4>

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
      "Metrics": {
        "StreamingEventCountPerSecond": 0,
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ],
  "AFIndexProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0
}
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[PISystemDto](#schemapisystemdto)|A `PISystemDto` object representing the PiSystem that was updated.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([PISystemDto](#schemapisystemdto))

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
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ],
  "AFIndexProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0
}
```

---

## `Set PIPoints Referenced By AF`

<a id="opIdDataSources_Set PIPoints Referenced By AF"></a>

Assign PI points referenced by AF to the Transfer specified by `transferId`.

<h3>Request</h3>

```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/transfers/{transferId}/pointsFromAF
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>`string transferId`
<br/>The Id of the Transfer" to be updated.<br/><br/>

<h4>Request Body</h4>

The updated set of points referenced by AF.<br/>

```json
[
  0
]
```

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[TransferDto](#schematransferdto)|Success: returns a `TransferDto` object representing the updated Transfer.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

<h4>Example response body</h4>

> 200 Response ([TransferDto](#schematransferdto))

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
  "AssetsCreatedCount": 0,
  "AssetsUpdatedCount": 0,
  "AssetsFailedCount": 0,
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
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string"
}
```

---

## `Delete PISystem`

<a id="opIdDataSources_Delete PISystem"></a>

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/{piSystemName}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the requested DataSource.<br/><br/>`string agentId`
<br/>The Id of the requested Agent.<br/><br/>`string piSystemName`
<br/>The name of the requested PI System<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Delete PISystem By Server Id`

<a id="opIdDataSources_Delete PISystem By Server Id"></a>

<h3>Request</h3>

```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/PISystems/PIServer/{piServerId}
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the requested DataSource.<br/><br/>`string agentId`
<br/>The Id of the requested Agent.<br/><br/>`string piServerId`
<br/>The id of the requested PI server<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|500|[ErrorResponse](#schemaerrorresponse)|None|

---

## `Agent AF Re Index`

<a id="opIdDataSources_Agent AF Re Index"></a>

Initiates the reindexing of the Agent specified by `agentId`.

<h3>Request</h3>

```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/pi/DataSources/{DataSourceId}/agents/{agentId}/reindexaf
```

<h4>Parameters</h4>

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string dataSourceId`
<br/>The Id of the DataSource the resource belongs to.<br/><br/>`string agentId`
<br/>The Id of the Agent the resource belongs to.<br/><br/>

<h3>Response</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success|
|500|[ErrorResponse](#schemaerrorresponse)|Internal Server Error|

---
## Definitions

### DataSourceDto

<a id="schemadatasourcedto"></a>
<a id="schema_DataSourceDto"></a>
<a id="tocSdatasourcedto"></a>
<a id="tocsdatasourcedto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|TenantId|guid|false|false|None|
|OcsNamespace|string|false|true|None|
|Agent|[AgentDto](#schemaagentdto)|false|true|None|

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
            "HistoricalEventCountPerSecond": 0,
            "SuccessfulCreations": 0,
            "FailedCreations": 0,
            "TotalPoints": 0,
            "AssetsCreatedPerSecond": 0,
            "AssetsProcessedCount": 0,
            "TotalAssetsInTransfer": 0
          },
          "Name": "string",
          "MetadataPrivacy": 0
        }
      ],
      "AFIndexProgress": 0,
      "ElementsIndexed": 0,
      "TotalElements": 0
    },
    "Namespace": "string",
    "Region": "string",
    "IsDeprecated": true,
    "TransferMetrics": {
      "StreamingEventCountPerSecond": 0,
      "HistoricalEventCountPerSecond": 0,
      "SuccessfulCreations": 0,
      "FailedCreations": 0,
      "TotalPoints": 0,
      "AssetsCreatedPerSecond": 0,
      "AssetsProcessedCount": 0,
      "TotalAssetsInTransfer": 0
    }
  }
}

```

---

### AgentDto

<a id="schemaagentdto"></a>
<a id="schema_AgentDto"></a>
<a id="tocSagentdto"></a>
<a id="tocsagentdto"></a>

<h4>Properties</h4>

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
|TransferMetrics|[TransferMetricsDto](#schematransfermetricsdto)|false|true|None|

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
        "Status": 0,
        "LatestStreamingRead": "2019-08-24T14:15:22Z",
        "OnPremTransferStatus": 0,
        "PIPointCount": 0,
        "Metrics": {
          "StreamingEventCountPerSecond": 0,
          "HistoricalEventCountPerSecond": 0,
          "SuccessfulCreations": 0,
          "FailedCreations": 0,
          "TotalPoints": 0,
          "AssetsCreatedPerSecond": 0,
          "AssetsProcessedCount": 0,
          "TotalAssetsInTransfer": 0
        },
        "Name": "string",
        "MetadataPrivacy": 0
      }
    ],
    "AFIndexProgress": 0,
    "ElementsIndexed": 0,
    "TotalElements": 0
  },
  "Namespace": "string",
  "Region": "string",
  "IsDeprecated": true,
  "TransferMetrics": {
    "StreamingEventCountPerSecond": 0,
    "HistoricalEventCountPerSecond": 0,
    "SuccessfulCreations": 0,
    "FailedCreations": 0,
    "TotalPoints": 0,
    "AssetsCreatedPerSecond": 0,
    "AssetsProcessedCount": 0,
    "TotalAssetsInTransfer": 0
  }
}

```

---

### AgentStatus

<a id="schemaagentstatus"></a>
<a id="schema_AgentStatus"></a>
<a id="tocSagentstatus"></a>
<a id="tocsagentstatus"></a>

<h4>Enumerated Values</h4>

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

---

### PISystemDto

<a id="schemapisystemdto"></a>
<a id="schema_PISystemDto"></a>
<a id="tocSpisystemdto"></a>
<a id="tocspisystemdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ServerId|guid|false|false|None|
|Name|string|false|true|None|
|Version|string|false|true|None|
|AFServerId|guid|false|false|None|
|AFName|string|false|true|None|
|AFVersion|string|false|true|None|
|LastCommunicationTime|date-time|false|false|None|
|Transfers|[[TransferSummaryDto](#schematransfersummarydto)]|false|true|[Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability]|
|AFIndexProgress|[AFIndexProgress](#schemaafindexprogress)|false|false|None|
|ElementsIndexed|int64|false|false|None|
|TotalElements|int64|false|false|None|

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
        "HistoricalEventCountPerSecond": 0,
        "SuccessfulCreations": 0,
        "FailedCreations": 0,
        "TotalPoints": 0,
        "AssetsCreatedPerSecond": 0,
        "AssetsProcessedCount": 0,
        "TotalAssetsInTransfer": 0
      },
      "Name": "string",
      "MetadataPrivacy": 0
    }
  ],
  "AFIndexProgress": 0,
  "ElementsIndexed": 0,
  "TotalElements": 0
}

```

---

### TransferSummaryDto

<a id="schematransfersummarydto"></a>
<a id="schema_TransferSummaryDto"></a>
<a id="tocStransfersummarydto"></a>
<a id="tocstransfersummarydto"></a>

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability

<h4>Properties</h4>

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
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out|

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
    "HistoricalEventCountPerSecond": 0,
    "SuccessfulCreations": 0,
    "FailedCreations": 0,
    "TotalPoints": 0,
    "AssetsCreatedPerSecond": 0,
    "AssetsProcessedCount": 0,
    "TotalAssetsInTransfer": 0
  },
  "Name": "string",
  "MetadataPrivacy": 0
}

```

---

### TransferStatus

<a id="schematransferstatus"></a>
<a id="schema_TransferStatus"></a>
<a id="tocStransferstatus"></a>
<a id="tocstransferstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|Description|
|---|---|---|
|NotSet|0||
|Started|1||
|Stopped|2||
|Initializing|3||

---

### TransferJobStatus

<a id="schematransferjobstatus"></a>
<a id="schema_TransferJobStatus"></a>
<a id="tocStransferjobstatus"></a>
<a id="tocstransferjobstatus"></a>

<h4>Enumerated Values</h4>

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
|NoValidPIPointsInTransfer|4096|
|UpdatingTransfer|8192|

---

### TransferMetricsDto

<a id="schematransfermetricsdto"></a>
<a id="schema_TransferMetricsDto"></a>
<a id="tocStransfermetricsdto"></a>
<a id="tocstransfermetricsdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|StreamingEventCountPerSecond|float|false|false|None|
|HistoricalEventCountPerSecond|float|false|false|None|
|SuccessfulCreations|int64|false|false|None|
|FailedCreations|int64|false|false|None|
|TotalPoints|int64|false|false|None|
|AssetsCreatedPerSecond|float|false|false|None|
|AssetsProcessedCount|int64|false|false|None|
|TotalAssetsInTransfer|int64|false|false|None|

```json
{
  "StreamingEventCountPerSecond": 0,
  "HistoricalEventCountPerSecond": 0,
  "SuccessfulCreations": 0,
  "FailedCreations": 0,
  "TotalPoints": 0,
  "AssetsCreatedPerSecond": 0,
  "AssetsProcessedCount": 0,
  "TotalAssetsInTransfer": 0
}

```

---

### DataPrivacy

<a id="schemadataprivacy"></a>
<a id="schema_DataPrivacy"></a>
<a id="tocSdataprivacy"></a>
<a id="tocsdataprivacy"></a>

None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out

<h4>Enumerated Values</h4>

|Property|Value|Description|
|---|---|---|
|Undefined|0||
|Medium|1||
|None|2||
|High|3||
|Low|4||

---

### AFIndexProgress

<a id="schemaafindexprogress"></a>
<a id="schema_AFIndexProgress"></a>
<a id="tocSafindexprogress"></a>
<a id="tocsafindexprogress"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|NotStarted|0|
|AFIndexInProgress|1|
|AFIndexingFailed|2|
|AFIndexingSucceeded|3|
|Restarting|4|

---

### ErrorResponse

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|None|
|Error|string|true|false|None|
|Reason|string|true|false|None|
|Resolution|string|true|false|None|
|DynamicProperties|object|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "DynamicProperties": {
    "property1": null,
    "property2": null
  },
  "property1": null,
  "property2": null
}

```

---

### TransferDto

<a id="schematransferdto"></a>
<a id="schema_TransferDto"></a>
<a id="tocStransferdto"></a>
<a id="tocstransferdto"></a>

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability

<h4>Properties</h4>

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
|AssetsCreatedCount|int32|false|false|None|
|AssetsUpdatedCount|int32|false|false|None|
|AssetsFailedCount|int32|false|false|None|
|OnPremTransferStatus|[TransferJobStatus](#schematransferjobstatus)|false|false|None|
|DesiredStatus|[TransferStatus](#schematransferstatus)|false|false|None|
|PIPointIds|[integer]|false|true|None|
|AFElementIds|string[]|false|true|None|
|PIPointsReferencedByAF|[integer]|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out|
|TransferRevisionNumber|int32|false|false|None|
|LastEditDate|date-time|false|false|None|
|LastEditBy|guid|false|false|None|

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
  "AssetsCreatedCount": 0,
  "AssetsUpdatedCount": 0,
  "AssetsFailedCount": 0,
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
  "Name": "string",
  "MetadataPrivacy": 0,
  "TransferRevisionNumber": 0,
  "LastEditDate": "2019-08-24T14:15:22Z",
  "LastEditBy": "string"
}

```

---

### AgentStatusDto

<a id="schemaagentstatusdto"></a>
<a id="schema_AgentStatusDto"></a>
<a id="tocSagentstatusdto"></a>
<a id="tocsagentstatusdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Agent|[ExternalFacingStatus](#schemaexternalfacingstatus)|false|true|None|
|AssetFrameworkIndexing|[ExternalFacingStatus](#schemaexternalfacingstatus)|false|true|None|
|Transfers|object|false|true|Status of each Transfer, keyed on the Transfer's ID|

```json
{
  "Agent": {
    "HealthStatus": 0,
    "InternalStatus": [
      "string"
    ]
  },
  "AssetFrameworkIndexing": {
    "HealthStatus": 0,
    "InternalStatus": [
      "string"
    ]
  },
  "Transfers": {
    "property1": {
      "HealthStatus": 0,
      "InternalStatus": [
        "string"
      ]
    },
    "property2": {
      "HealthStatus": 0,
      "InternalStatus": [
        "string"
      ]
    }
  }
}

```

---

### ExternalFacingStatus

<a id="schemaexternalfacingstatus"></a>
<a id="schema_ExternalFacingStatus"></a>
<a id="tocSexternalfacingstatus"></a>
<a id="tocsexternalfacingstatus"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HealthStatus|[ConsolidatedStatus](#schemaconsolidatedstatus)|false|false|None|
|InternalStatus|string[]|false|true|None|

```json
{
  "HealthStatus": 0,
  "InternalStatus": [
    "string"
  ]
}

```

---

### ConsolidatedStatus

<a id="schemaconsolidatedstatus"></a>
<a id="schema_ConsolidatedStatus"></a>
<a id="tocSconsolidatedstatus"></a>
<a id="tocsconsolidatedstatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Starting|0|
|Running|1|
|Succeeded|2|
|Warning|3|
|Failed|4|

---

### QueryDto

<a id="schemaquerydto"></a>
<a id="schema_QueryDto"></a>
<a id="tocSquerydto"></a>
<a id="tocsquerydto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|QueryType|[QueryTypes](#schemaquerytypes)|false|false|None|
|PI|[QueryPIDto](#schemaquerypidto)|false|true|None|
|AF|[QueryAFDto](#schemaqueryafdto)|false|true|None|
|Status|[QueryStatus](#schemaquerystatus)|false|false|None|
|Skip|int32|false|false|None|
|Count|int32|false|false|None|

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
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

### QueryTypes

<a id="schemaquerytypes"></a>
<a id="schema_QueryTypes"></a>
<a id="tocSquerytypes"></a>
<a id="tocsquerytypes"></a>

<h4>Enumerated Values</h4>

|Property|Value|Description|
|---|---|---|
|None|0|undefined|
|PIPoint|1|undefined|
|AFDatabases|2|undefined|
|AFHierarchy|4|undefined|
|PIPointList|8|undefined|
|AFElementList|16|undefined|
|AFElementSearchByAttribute|32|undefined|
|AFAttributeLoad|64|undefined|
|AFElementReferencedPIPoints|128|undefined|
|PIPointListEx|256|undefined|
|ValidateAFOnlyTransfer|512|undefined|

---

### QueryPIDto

<a id="schemaquerypidto"></a>
<a id="schema_QueryPIDto"></a>
<a id="tocSquerypidto"></a>
<a id="tocsquerypidto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointMasks|object|false|true|None|
|PointIds|[integer]|false|true|None|
|PointList|[QueryPIPointListExDto](#schemaquerypipointlistexdto)|false|true|None|

```json
{
  "PointMasks": {
    "property1": "string",
    "property2": "string"
  },
  "PointIds": [
    0
  ],
  "PointList": {
    "MetadataPrivacy": 0,
    "PointIds": [
      0
    ]
  }
}

```

---

### QueryPIPointListExDto

<a id="schemaquerypipointlistexdto"></a>
<a id="schema_QueryPIPointListExDto"></a>
<a id="tocSquerypipointlistexdto"></a>
<a id="tocsquerypipointlistexdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out|
|PointIds|[integer]|false|true|None|

```json
{
  "MetadataPrivacy": 0,
  "PointIds": [
    0
  ]
}

```

---

### QueryAFDto

<a id="schemaqueryafdto"></a>
<a id="schema_QueryAFDto"></a>
<a id="tocSqueryafdto"></a>
<a id="tocsqueryafdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HierarchyMasks|object|false|true|None|
|ElementSearchByAttributeMasks|object|false|true|None|
|ObjectIds|string[]|false|true|None|

```json
{
  "HierarchyMasks": {
    "property1": "string",
    "property2": "string"
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

---

### QueryHierarchyMask

<a id="schemaqueryhierarchymask"></a>
<a id="schema_QueryHierarchyMask"></a>
<a id="tocSqueryhierarchymask"></a>
<a id="tocsqueryhierarchymask"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|DatabaseId|1|
|Id|2|
|TreePath|3|
|Skip|4|
|Count|5|

---

### QueryElementSearchByAttributeMask

<a id="schemaqueryelementsearchbyattributemask"></a>
<a id="schema_QueryElementSearchByAttributeMask"></a>
<a id="tocSqueryelementsearchbyattributemask"></a>
<a id="tocsqueryelementsearchbyattributemask"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|DatabaseId|1|
|QueryString|2|
|AttributeName|3|

---

### QueryStatus

<a id="schemaquerystatus"></a>
<a id="schema_QueryStatus"></a>
<a id="tocSquerystatus"></a>
<a id="tocsquerystatus"></a>

<h4>Enumerated Values</h4>

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

---

### PIPointQueryDto

<a id="schemapipointquerydto"></a>
<a id="schema_PIPointQueryDto"></a>
<a id="tocSpipointquerydto"></a>
<a id="tocspipointquerydto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|guid|false|false|None|
|PointNameMask|string|false|true|None|
|PointSourceMask|string|false|true|None|
|Status|[PIPointQueryStatus](#schemapipointquerystatus)|false|false|None|

```json
{
  "Id": "string",
  "PointNameMask": "string",
  "PointSourceMask": "string",
  "Status": 0
}

```

---

### PIPointQueryStatus

<a id="schemapipointquerystatus"></a>
<a id="schema_PIPointQueryStatus"></a>
<a id="tocSpipointquerystatus"></a>
<a id="tocspipointquerystatus"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Ready|0|
|Querying|1|
|Completed|2|
|NotSupportedByAgent|3|

---

### QueryResultPageDto

<a id="schemaqueryresultpagedto"></a>
<a id="schema_QueryResultPageDto"></a>
<a id="tocSqueryresultpagedto"></a>
<a id="tocsqueryresultpagedto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Results|[any]|false|true|None|
|AdditionalInformation|object|false|true|None|

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

### PIPointQueryResultDto

<a id="schemapipointqueryresultdto"></a>
<a id="schema_PIPointQueryResultDto"></a>
<a id="tocSpipointqueryresultdto"></a>
<a id="tocspipointqueryresultdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ResultPIPointsAttributes|[[PIPointAttributesFromQueryResult](#schemapipointattributesfromqueryresult)]|false|true|None|

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

### PIPointAttributesFromQueryResult

<a id="schemapipointattributesfromqueryresult"></a>
<a id="schema_PIPointAttributesFromQueryResult"></a>
<a id="tocSpipointattributesfromqueryresult"></a>
<a id="tocspipointattributesfromqueryresult"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointId|int32|false|false|None|
|Name|string|false|true|None|
|PointSource|string|false|true|None|
|Description|string|false|true|None|
|EngineeringUnits|string|false|true|None|

```json
{
  "PointId": 0,
  "Name": "string",
  "PointSource": "string",
  "Description": "string",
  "EngineeringUnits": "string"
}

```

---

### Capability

<a id="schemacapability"></a>
<a id="schema_Capability"></a>
<a id="tocScapability"></a>
<a id="tocscapability"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|id|string|false|true|None|
|ver|int32|false|false|None|
|en|boolean|false|false|None|

```json
{
  "id": "string",
  "ver": 0,
  "en": true
}

```

---

### DataSourceCreateUpdateDto

<a id="schemadatasourcecreateupdatedto"></a>
<a id="schema_DataSourceCreateUpdateDto"></a>
<a id="tocSdatasourcecreateupdatedto"></a>
<a id="tocsdatasourcecreateupdatedto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|true|false|None|
|Description|string|false|true|None|

```json
{
  "Name": "string",
  "Description": "string"
}

```

---

### TransferCreateDto

<a id="schematransfercreatedto"></a>
<a id="schema_TransferCreateDto"></a>
<a id="tocStransfercreatedto"></a>
<a id="tocstransfercreatedto"></a>

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|HistoricalDataStartTime|date-time|true|false|None|
|Description|string|false|true|None|
|PIPointIds|[integer]|false|true|None|
|AFElementIds|string[]|false|true|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out|

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

---

### QueryCreateUpdateDto

<a id="schemaquerycreateupdatedto"></a>
<a id="schema_QueryCreateUpdateDto"></a>
<a id="tocSquerycreateupdatedto"></a>
<a id="tocsquerycreateupdatedto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|QueryType|[QueryTypes](#schemaquerytypes)|false|true|None|
|PI|[QueryPIDto](#schemaquerypidto)|false|true|None|
|AF|[QueryAFDto](#schemaqueryafdto)|false|true|None|
|Skip|int32|false|false|None|
|Count|int32|false|false|None|

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
    ],
    "PointList": {
      "MetadataPrivacy": 0,
      "PointIds": [
        0
      ]
    }
  },
  "AF": {
    "HierarchyMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ElementSearchByAttributeMasks": {
      "property1": "string",
      "property2": "string"
    },
    "ObjectIds": [
      "string"
    ]
  },
  "Skip": 2147483647,
  "Count": 2147483647
}

```

---

### PatchDto

<a id="schemapatchdto"></a>
<a id="schema_PatchDto"></a>
<a id="tocSpatchdto"></a>
<a id="tocspatchdto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|op|[PatchOperation](#schemapatchoperation)|true|false|None|
|path|string|false|false|None|
|value|any|false|true|None|

```json
{
  "op": 1,
  "path": "string",
  "value": null
}

```

---

### PatchOperation

<a id="schemapatchoperation"></a>
<a id="schema_PatchOperation"></a>
<a id="tocSpatchoperation"></a>
<a id="tocspatchoperation"></a>

<h4>Enumerated Values</h4>

|Property|Value|
|---|---|
|Add|1|
|Remove|2|
|Replace|3|
|Move|4|
|Copy|5|
|Test|6|

---

### PIPointQueryCreateUpdateDto

<a id="schemapipointquerycreateupdatedto"></a>
<a id="schema_PIPointQueryCreateUpdateDto"></a>
<a id="tocSpipointquerycreateupdatedto"></a>
<a id="tocspipointquerycreateupdatedto"></a>

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|PointNameMask|string|true|false|None|
|PointSourceMask|string|true|false|None|

```json
{
  "PointNameMask": "string",
  "PointSourceMask": "string"
}

```

---

### TransferUpdateDto

<a id="schematransferupdatedto"></a>
<a id="schema_TransferUpdateDto"></a>
<a id="tocStransferupdatedto"></a>
<a id="tocstransferupdatedto"></a>

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Description|string|false|true|None|
|DesiredStatus|[TransferStatus](#schematransferstatus)|false|false|None|
|Name|string|false|true|None|
|MetadataPrivacy|[DataPrivacy](#schemadataprivacy)|false|false|None means all metadata is filtered out Low filters all but 3 metadata items Medium only filters out 2 metadata items High means no data is filtered out|
|PIPointIds|[integer]|false|true|None|
|AFElementIds|string[]|false|true|None|
|HistoricalDataStartTime|date-time|false|true|None|

```json
{
  "Description": "string",
  "DesiredStatus": 0,
  "Name": "string",
  "MetadataPrivacy": 0,
  "PIPointIds": [
    0
  ],
  "AFElementIds": [
    "string"
  ],
  "HistoricalDataStartTime": "2019-08-24T14:15:22Z"
}

```

---

### TransferUpdateStatusDto

<a id="schematransferupdatestatusdto"></a>
<a id="schema_TransferUpdateStatusDto"></a>
<a id="tocStransferupdatestatusdto"></a>
<a id="tocstransferupdatestatusdto"></a>

Before making additions or any modifications to this class, please consult the following article to maintain best practice: https://dev.azure.com/osieng/engineering/_wiki/wikis/pitoocs.wiki/17354/Models-and-Backwards-Compatability

<h4>Properties</h4>

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|DesiredStatus|[TransferStatus](#schematransferstatus)|false|false|None|

```json
{
  "DesiredStatus": 0
}

```

---

