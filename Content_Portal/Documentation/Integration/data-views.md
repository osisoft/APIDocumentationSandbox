---
title: Integration/data-views v20210407.2
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: osisoft.widdershins v1.0.7

---

# Data Views
APIs for working with Data Views

## List All

<a id="opIdDataViews_List All"></a>

Returns a list of data views.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>
`[optional] integer skip`
<br/>An optional parameter representing the zero-based offset of the first data view to retrieve. If not specified, a default value of 0 is used.<br/><br/>`[optional] integer count`
<br/>An optional parameter representing the maximum number of data views to retrieve. If not specified, a default value of 100 is used.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataView](#schemadataview)[]|A page of data views. A response header, Total-Count, indicates the total size of the collection.|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of data views visible to the current user|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable|
|200|Next-Page|integer|Hyperlink to the next page of results|
|200|First-Page|integer|Hyperlink to the first page of results|

#### Example response body
> 200 Response

```json
{
  "TypeId": "SimpleType",
  "Id": "SimpleStream",
  "Name": "SimpleStream"
}
```

> 500 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}
```

---

## Create

<a id="opIdDataViews_Create"></a>

Create a new data view with a system-generated identifier.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>

### Request Body

A DataView object whose Id is null or unspecified<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.|
|403|[ResultError](#schemaresulterror)|You are not authorized to create a data view|
|404|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Example response body
> 201 Response

```
"Namespace identifier"
```

> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}
```

---

## Get

<a id="opIdDataViews_Get"></a>

Get a Data View by id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>`string id`
<br/>The data view identifier<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataView](#schemadataview)|The requested data view.|
|403|[ResultError](#schemaresulterror)|You are not authorized to view the requested data view|
|404|[ResultError](#schemaresulterror)|The specified data view identifier is not found|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Example response body
> 200 Response

```json
{
  "TypeId": "SimpleType",
  "Id": "SimpleStream",
  "Name": "SimpleStream"
}
```

> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}
```

---

## Create (`id` path)

<a id="opIdDataViews_Create (`id` path)"></a>

This call creates the specified data view. If a data view with the same id already exists, the existing data view is compared with the specified data view. If they are identical, a redirect (302 Found) is returned with the Location response header indicating the URL where the data view may be retrieved using a Get function. If the data views do not match, the request fails with 409 Conflict.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>`string id`
<br/>The data view identifier<br/><br/>

### Request Body

A DataView object whose Id is null or unspecified<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.|
|302|None|The specified data view already exists. A response header, Location, indicates the URL where the data view may be retrieved with the GET verb|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation|
|409|[ResultError](#schemaresulterror)|The specified data view conflicts with an existing data view that is not identical. To forcibly update the data view, see Create Or Update Data View|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": 0,
          "Keys": [
            "string"
          ],
          "StreamReferenceNames": [
            "string"
          ],
          "Label": "string",
          "SummaryType": 0,
          "SummaryDirection": null,
          "IncludeUom": true
        }
      ],
      "IdentifyingField": {
        "Source": "[",
        "Keys": [
          null
        ],
        "StreamReferenceNames": [
          null
        ],
        "Label": "string",
        "SummaryType": "[",
        "SummaryDirection": null,
        "IncludeUom": true
      }
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

---

## Create Or Update

<a id="opIdDataViews_Create Or Update"></a>

If a data view with the same id already exists, it is updated to the specified value. Otherwise, a new data view is created.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>`string id`
<br/>The data view identifier<br/><br/>

### Request Body

A DataView object whose Id matches the dataViewId in the URL.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": null,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": null,
          "Keys": null,
          "StreamReferenceNames": null,
          "Label": null,
          "SummaryType": null,
          "SummaryDirection": null,
          "IncludeUom": null
        }
      ],
      "IdentifyingField": {}
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": "[",
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.|
|204|None|Successfully updated the data view|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation|
|409|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Example response body
> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": 0,
          "Keys": [
            "string"
          ],
          "StreamReferenceNames": [
            "string"
          ],
          "Label": "string",
          "SummaryType": 0,
          "SummaryDirection": null,
          "IncludeUom": true
        }
      ],
      "IdentifyingField": {
        "Source": "[",
        "Keys": [
          null
        ],
        "StreamReferenceNames": [
          null
        ],
        "Label": "string",
        "SummaryType": "[",
        "SummaryDirection": null,
        "IncludeUom": true
      }
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}
```

---

## Delete

<a id="opIdDataViews_Delete"></a>

Delete the data view with the specified id.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>The tenant identifier<br/><br/>`string namespaceId`
<br/>The namespace identifier<br/><br/>`string id`
<br/>The data view identifier<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Successfully updated the data view|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation|
|404|[ResultError](#schemaresulterror)|The specified data view identifier is not found|
|409|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details|

#### Example response body
> 403 Response

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}
```

---

## Get Data View Acl

<a id="opIdDataViews_Get Data View Acl"></a>

Get the Data View Access Control List for Data View with specified Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|OK - retrieved the Data View Access Control List. See [Access Control Lists](..\Access_Control.md#access-control-lists) for object structure and more information about ACLs.|

---

## Update Data View Acl

<a id="opIdDataViews_Update Data View Acl"></a>

Update the Data View Access Control List for Data View with specified Id

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>

### Request Body

Updated Access Control List. See [Access Control Lists](..\Access_Control.md#access-control-lists) for object structure and more information about ACLs.<br/>

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {},
      "AccessType": 0,
      "AccessRights": 0
    }
  ]
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Data View Access Rights

<a id="opIdDataViews_Get Data View Access Rights"></a>

Get the calling user or client's access rights for Data View with specified Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accessrights
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Data Interpolated

<a id="opIdDataViews_Get Data Interpolated"></a>

Get data for the provided index parameters with paging

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/data/interpolated
?startIndex={startIndex}&endIndex={endIndex}&interval={interval}&form={form}&continuationToken={continuationToken}&count={count}&cache={cache}
```

#### Parameters

`string tenantId`
<br/><br/>`string namespaceId`
<br/><br/>`string id`
<br/><br/>`string startIndex`
<br/><br/>`string endIndex`
<br/><br/>`string interval`
<br/><br/>`string form`
<br/><br/>`string continuationToken`
<br/><br/>`integer count`
<br/><br/>
`[optional] string cache`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Data View Owner

<a id="opIdDataViews_Get Data View Owner"></a>

Get the Data View owner for Data View with specified Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Update Data View Owner

<a id="opIdDataViews_Update Data View Owner"></a>

Update the Data View owner for Data View with specified Id

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>

### Request Body

Updated owner. See [Owner](..\Access_Control.md#owner) for object structure more information about Owners.<br/>

```json
{
  "Type": 1,
  "ObjectId": "string",
  "TenantId": "string"
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Available Field Sets

<a id="opIdDataViews_Get Available Field Sets"></a>

Get available field sets for Data View with specified Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/availablefieldsets
?cache={cache}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>
`[optional] string cache`
<br/>Cache preserve or cache refresh<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Data Items

<a id="opIdDataViews_Get Data Items"></a>

Get data items for a dataview by Query Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/dataitems/{queryid}
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of the dataview<br/><br/>`string queryId`
<br/>Id of the query<br/><br/>
`[optional] string cache`
<br/>Specifies if Data View backing resources are to be refreshed. See [Retrieving Data](DataRetrieval.md)<br/><br/>`[optional] integer skip`
<br/>The number of data items to skip<br/><br/>`[optional] integer count`
<br/>The number of data items to display per page. Maximum count allowed is 1000<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Field Mappings

<a id="opIdDataViews_Get Field Mappings"></a>

Get field mappings for a specified Data View

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/fieldmappings
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of dataview<br/><br/>
`[optional] string cache`
<br/>Specifies if Data View backing resources are to be refreshed. See [Retrieving Data](DataRetrieval.md)<br/><br/>`[optional] integer skip`
<br/>The number of data groups to skip<br/><br/>`[optional] integer count`
<br/>The number of data groups to display per page. Maximum count allowed is 1000<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Groups

<a id="opIdDataViews_Get Groups"></a>

Get Data Groups for a specified Data View

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/groups
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of dataview<br/><br/>
`[optional] string cache`
<br/>Specifies if Data View backing resources are to be refreshed. See [Retrieving Data](DataRetrieval.md)<br/><br/>`[optional] integer skip`
<br/>The number of data groups to skip<br/><br/>`[optional] integer count`
<br/>The number of data groups to display per page. Maximum count allowed is 1000<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Ineligible Data Items

<a id="opIdDataViews_Get Ineligible Data Items"></a>

Get ineligible data items for a dataview by Query Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/ineligibledataitems/{queryid}
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of the dataview<br/><br/>`string queryId`
<br/>Id of the query<br/><br/>
`[optional] string cache`
<br/>Specifies if Data View backing resources are to be refreshed. See [Retrieving Data](DataRetrieval.md)<br/><br/>`[optional] integer skip`
<br/>The number of data items to skip<br/><br/>`[optional] integer count`
<br/>The number of data items to display per page. Maximum count allowed is 1000<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---

## Get Statistics

<a id="opIdDataViews_Get Statistics"></a>

Get available field sets for Data View with specified Id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/statistics
?cache={cache}
```

#### Parameters

`string tenantId`
<br/>Id of tenant<br/><br/>`string namespaceId`
<br/>Id of namespace<br/><br/>`string id`
<br/>Id of Data View<br/><br/>
`[optional] string cache`
<br/>Cache preserve or cache refresh<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|None|

---
# Definitions

## DataView

<a id="schemadataview"></a>
<a id="schema_DataView"></a>
<a id="tocSdataview"></a>
<a id="tocsdataview"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|IndexField|[Field](#schemafield)|false|true|None|
|Queries|[[Query](#schemaquery)]|false|true|None|
|DataFieldSets|[[FieldSet](#schemafieldset)]|false|true|None|
|GroupingFields|[[Field](#schemafield)]|false|true|None|
|DefaultStartIndex|string|false|true|None|
|DefaultEndIndex|string|false|true|None|
|DefaultInterval|string|false|true|None|
|IndexTypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Shape|[DataViewShape](#schemadataviewshape)|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "IndexField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  },
  "Queries": [
    {
      "Id": "string",
      "Kind": 1,
      "Value": "string"
    }
  ],
  "DataFieldSets": [
    {
      "QueryId": "string",
      "DataFields": [
        {
          "Source": 0,
          "Keys": [
            "string"
          ],
          "StreamReferenceNames": [
            "string"
          ],
          "Label": "string",
          "SummaryType": 0,
          "SummaryDirection": null,
          "IncludeUom": true
        }
      ],
      "IdentifyingField": {
        "Source": "[",
        "Keys": [
          null
        ],
        "StreamReferenceNames": [
          null
        ],
        "Label": "string",
        "SummaryType": "[",
        "SummaryDirection": null,
        "IncludeUom": true
      }
    }
  ],
  "GroupingFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "DefaultStartIndex": "string",
  "DefaultEndIndex": "string",
  "DefaultInterval": "string",
  "IndexTypeCode": 0,
  "Shape": 0
}

```

---

## Field

<a id="schemafield"></a>
<a id="schema_Field"></a>
<a id="tocSfield"></a>
<a id="tocsfield"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Source|[FieldSource](#schemafieldsource)|false|false|None|
|Keys|string[]|false|true|None|
|StreamReferenceNames|string[]|false|true|None|
|Label|string|false|true|None|
|SummaryType|[SdsSummaryType](#schemasdssummarytype)|false|false|None|
|SummaryDirection|[SummaryDirection](#schemasummarydirection)|false|true|None|
|IncludeUom|boolean|false|false|None|

```json
{
  "Source": 0,
  "Keys": [
    "string"
  ],
  "StreamReferenceNames": [
    "string"
  ],
  "Label": "string",
  "SummaryType": 0,
  "SummaryDirection": 1,
  "IncludeUom": true
}

```

---

## FieldSource

<a id="schemafieldsource"></a>
<a id="schema_FieldSource"></a>
<a id="tocSfieldsource"></a>
<a id="tocsfieldsource"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|NotApplicable|0|
|Id|1|
|Name|2|
|PropertyId|3|
|PropertyName|4|
|Metadata|5|
|Tags|6|

---

## SdsSummaryType

<a id="schemasdssummarytype"></a>
<a id="schema_SdsSummaryType"></a>
<a id="tocSsdssummarytype"></a>
<a id="tocssdssummarytype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|None|0|
|Count|1|
|Minimum|2|
|Maximum|4|
|Range|8|
|Mean|16|
|StandardDeviation|32|
|PopulationStandardDeviation|64|
|Total|128|
|Skewness|256|
|Kurtosis|512|
|WeightedMean|1024|
|WeightedStandardDeviation|2048|
|WeightedPopulationStandardDeviation|4096|

---

## SummaryDirection

<a id="schemasummarydirection"></a>
<a id="schema_SummaryDirection"></a>
<a id="tocSsummarydirection"></a>
<a id="tocssummarydirection"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Forward|1|
|Backward|2|

---

## Query

<a id="schemaquery"></a>
<a id="schema_Query"></a>
<a id="tocSquery"></a>
<a id="tocsquery"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Kind|[DataItemResourceType](#schemadataitemresourcetype)|false|false|None|
|Value|string|false|true|None|

```json
{
  "Id": "string",
  "Kind": 1,
  "Value": "string"
}

```

---

## DataItemResourceType

<a id="schemadataitemresourcetype"></a>
<a id="schema_DataItemResourceType"></a>
<a id="tocSdataitemresourcetype"></a>
<a id="tocsdataitemresourcetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Stream|1|
|Asset|2|

---

## FieldSet

<a id="schemafieldset"></a>
<a id="schema_FieldSet"></a>
<a id="tocSfieldset"></a>
<a id="tocsfieldset"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|QueryId|string|false|true|None|
|DataFields|[[Field](#schemafield)]|false|true|None|
|IdentifyingField|[Field](#schemafield)|false|true|None|

```json
{
  "QueryId": "string",
  "DataFields": [
    {
      "Source": 0,
      "Keys": [
        "string"
      ],
      "StreamReferenceNames": [
        "string"
      ],
      "Label": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "IncludeUom": true
    }
  ],
  "IdentifyingField": {
    "Source": 0,
    "Keys": [
      "string"
    ],
    "StreamReferenceNames": [
      "string"
    ],
    "Label": "string",
    "SummaryType": 0,
    "SummaryDirection": 1,
    "IncludeUom": true
  }
}

```

---

## SdsTypeCode

<a id="schemasdstypecode"></a>
<a id="schema_SdsTypeCode"></a>
<a id="tocSsdstypecode"></a>
<a id="tocssdstypecode"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Empty|0|
|Object|1|
|Boolean|3|
|Char|4|
|SByte|5|
|Byte|6|
|Int16|7|
|UInt16|8|
|Int32|9|
|UInt32|10|
|Int64|11|
|UInt64|12|
|Single|13|
|Double|14|
|Decimal|15|
|DateTime|16|
|String|18|
|Guid|19|
|DateTimeOffset|20|
|TimeSpan|21|
|Version|22|
|NullableBoolean|103|
|NullableChar|104|
|NullableSByte|105|
|NullableByte|106|
|NullableInt16|107|
|NullableUInt16|108|
|NullableInt32|109|
|NullableUInt32|110|
|NullableInt64|111|
|NullableUInt64|112|
|NullableSingle|113|
|NullableDouble|114|
|NullableDecimal|115|
|NullableDateTime|116|
|NullableGuid|119|
|NullableDateTimeOffset|120|
|NullableTimeSpan|121|
|BooleanArray|203|
|CharArray|204|
|SByteArray|205|
|ByteArray|206|
|Int16Array|207|
|UInt16Array|208|
|Int32Array|209|
|UInt32Array|210|
|Int64Array|211|
|UInt64Array|212|
|SingleArray|213|
|DoubleArray|214|
|DecimalArray|215|
|DateTimeArray|216|
|StringArray|218|
|GuidArray|219|
|DateTimeOffsetArray|220|
|TimeSpanArray|221|
|VersionArray|222|
|Array|400|
|IList|401|
|IDictionary|402|
|IEnumerable|403|
|SdsType|501|
|SdsTypeProperty|502|
|SdsStreamView|503|
|SdsStreamViewProperty|504|
|SdsStreamViewMap|505|
|SdsStreamViewMapProperty|506|
|SdsStream|507|
|SdsStreamIndex|508|
|SdsTable|509|
|SdsColumn|510|
|SdsValues|511|
|SdsObject|512|
|SByteEnum|605|
|ByteEnum|606|
|Int16Enum|607|
|UInt16Enum|608|
|Int32Enum|609|
|UInt32Enum|610|
|Int64Enum|611|
|UInt64Enum|612|
|NullableSByteEnum|705|
|NullableByteEnum|706|
|NullableInt16Enum|707|
|NullableUInt16Enum|708|
|NullableInt32Enum|709|
|NullableUInt32Enum|710|
|NullableInt64Enum|711|
|NullableUInt64Enum|712|

---

## DataViewShape

<a id="schemadataviewshape"></a>
<a id="schema_DataViewShape"></a>
<a id="tocSdataviewshape"></a>
<a id="tocsdataviewshape"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Standard|0|
|Narrow|1|

---

## ResultError

<a id="schemaresulterror"></a>
<a id="schema_ResultError"></a>
<a id="tocSresulterror"></a>
<a id="tocsresulterror"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|Resolution|string|false|true|None|
|Kind|[ResultErrorKind](#schemaresulterrorkind)|false|false|None|
|Parameters|object|false|true|None|
|ChildErrors|[[ResultError](#schemaresulterror)]|false|true|None|

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "Kind": 0,
  "Parameters": {
    "property1": "string",
    "property2": "string"
  },
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "Kind": 0,
      "Parameters": {
        "property1": "string",
        "property2": "string"
      },
      "ChildErrors": [
        {
          "OperationId": "string",
          "Error": "string",
          "Reason": "string",
          "Resolution": "string",
          "Kind": 0,
          "Parameters": {
            "property1": "string",
            "property2": "string"
          },
          "ChildErrors": [
            {}
          ]
        }
      ]
    }
  ]
}

```

---

## ResultErrorKind

<a id="schemaresulterrorkind"></a>
<a id="schema_ResultErrorKind"></a>
<a id="tocSresulterrorkind"></a>
<a id="tocsresulterrorkind"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|UnspecifiedServerError|0|
|RequestInvalid|1|
|ResourceNotFound|2|
|OperationForbidden|3|
|OperationInvalid|4|
|OperationFailed|5|
|ResourceUnavailable|6|

---

## AccessControlList

<a id="schemaaccesscontrollist"></a>
<a id="schema_AccessControlList"></a>
<a id="tocSaccesscontrollist"></a>
<a id="tocsaccesscontrollist"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|RoleTrusteeAccessControlEntries|[[AccessControlEntry](#schemaaccesscontrolentry)]|false|true|None|

```json
{
  "RoleTrusteeAccessControlEntries": [
    {
      "Trustee": {
        "Type": "[",
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

## AccessControlEntry

<a id="schemaaccesscontrolentry"></a>
<a id="schema_AccessControlEntry"></a>
<a id="tocSaccesscontrolentry"></a>
<a id="tocsaccesscontrolentry"></a>

### Properties

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

## Trustee

<a id="schematrustee"></a>
<a id="schema_Trustee"></a>
<a id="tocStrustee"></a>
<a id="tocstrustee"></a>

### Properties

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

## TrusteeType

<a id="schematrusteetype"></a>
<a id="schema_TrusteeType"></a>
<a id="tocStrusteetype"></a>
<a id="tocstrusteetype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|User|1|
|Client|2|
|Role|3|

---

## AccessType

<a id="schemaaccesstype"></a>
<a id="schema_AccessType"></a>
<a id="tocSaccesstype"></a>
<a id="tocsaccesstype"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Allowed|0|
|Denied|1|

---

