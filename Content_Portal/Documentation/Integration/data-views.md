---
title: Integration/data-views v20210414.3
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

## List Data Views

<a id="opIdDataViews_List Data Views"></a>

Returns a list of data views.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews
?skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>
`[optional] integer skip`
<br/>An optional parameter representing the zero-based offset of the first data view to retrieve. If not specified, a default value of 0 is used.<br/><br/><br/>`[optional] integer count`
<br/>An optional parameter representing the maximum number of data views to retrieve. If not specified, a default value of 100 is used.<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataView](#schemadataview)[]|A page of data views. A response header, Total-Count, indicates the total size of the collection.<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of data views visible to the current user<br/>|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable<br/>|
|200|Next-Page|integer|Hyperlink to the next page of results<br/>|
|200|First-Page|integer|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
HTTP 201 Created
Content-Type: application/json  
{
  [
    {
      "Id": "demo view 1",
      ... etc.
    },
    {
      "Id": "demo view 2",
      ... etc.
    }
  ]
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

## Create Data View

<a id="opIdDataViews_Create Data View"></a>

Create a new data view with a system-generated identifier.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>

### Request Body

A DataView object whose Id is null or unspecified<br/><br/>

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
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to create a data view<br/>|
|404|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 201 Response

```json
HTTP 201 Created
Content-Type: application/json  
{
  "Id": "c79630cc-21dc-483e-8b37-46880e92c456",
  "Name": "demo",
  "Description": "demonstration",
  "IndexField": { "Label": "Timestamp" },
  "Queries": [],
  "DataFieldSets": [],
  "GroupingFields": [],
  "IndexTypeCode": "DateTime",
  "Shape": "Standard"
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

## Get Data View

<a id="opIdDataViews_Get Data View"></a>

Get a Data View by id

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[DataView](#schemadataview)|The requested data view.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to view the requested data view<br/>|
|404|[ResultError](#schemaresulterror)|The specified data view identifier is not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
Content-Type: application/json  
{
  "Id": "demo",
  "Name": "demo",
  "IndexField": { "Label": "Timestamp" },
  "Queries": [
    { 
      "Id": "weather",
      "Kind": "Stream",
      "Value":"*weather*" 
    }
  ],
  "DataFieldSets": [],
  "GroupingFields": [],
  "IndexTypeCode": "DateTime",
  "Shape": "Standard"
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

## Get or Create Data View

<a id="opIdDataViews_Get or Create Data View"></a>

This call creates the specified data view. If a data view with the same id already exists, the existing data view is compared with the specified data view. If they are identical, a redirect (302 Found) is returned with the Location response header indicating the URL where the data view may be retrieved using a Get function. If the data views do not match, the request fails with 409 Conflict.

### Request
```text 
POST /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

A DataView object whose Id is null or unspecified<br/><br/>

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
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.<br/>|
|302|None|The specified data view already exists. A response header, Location, indicates the URL where the data view may be retrieved with the GET verb<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|409|[ResultError](#schemaresulterror)|The specified data view conflicts with an existing data view that is not identical. To forcibly update the data view, see Create Or Update Data View<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 201 Response

```json
HTTP 201 Created
Content-Type: application/json  
{
  "Id": "demo2",
  "Name": "demo2",
  "Description": "demonstration 2",
  "IndexField": { "Label": "Timestamp" },
  "Queries": [],
  "DataFieldSets": [],
  "GroupingFields": [],
  "IndexTypeCode": "DateTime",
  "Shape": "Standard"
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

## Create or Update Data View

<a id="opIdDataViews_Create or Update Data View"></a>

If a data view with the same id already exists, it is updated to the specified value. Otherwise, a new data view is created.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

A DataView object whose Id matches the dataViewId in the URL.<br/><br/>

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
|201|[DataView](#schemadataview)|The data view as persisted, including values for optional parameters that were omitted in the request.<br/>|
|204|None|Successfully updated the data view<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|409|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

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

## Delete Data View

<a id="opIdDataViews_Delete Data View"></a>

Delete the data view with the specified id.

### Request
```text 
DELETE /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Successfully updated the data view<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The specified data view identifier is not found<br/>|
|409|[ResultError](#schemaresulterror)|None|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

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

## Get Data View Access Control List

<a id="opIdDataViews_Get Data View Access Control List"></a>

Get the `AccessControlList` of the specified data view

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[AccessControlList](#schemaaccesscontrollist)|The access control list of the requested data view<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to view the requested data view's access control list<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
{
  "RoleTrusteeAccessControlEntries": 
  [
    {
      "Trustee": {
        "Type": Role,
        "RoleId": "11111111-1111-1111-1111-111111111111"
      },
      "AccessType": Allowed,
      "AccessRights": 1
    },
    {
      "Trustee": {
        "Type": Role,
        "RoleId": "22222222-2222-2222-2222-222222222222"
      },
      "AccessType": Allowed,
      "AccessRights": 15
    },
    {
      "Trustee": {
        "Type": User,
        "RoleId": "33333333-3333-3333-3333-333333333333"
      },
      "AccessType": Denied,
      "AccessRights": 8
    }
  ]
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

## Update Data View Access Control List

<a id="opIdDataViews_Update Data View Access Control List"></a>

Update the `AccessControlList` of the specified data view.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accesscontrol
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

An [`AccessControlList`](xref:accessControl#access-control-lists)<br/>

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
|204|None|Successfully updated the data view access control list<br/>|
|400|[ResultError](#schemaresulterror)|The request is not valid. See the response body for details<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to update the requested data view's access control list<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 400 Response

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

## List Data View Access Rights

<a id="opIdDataViews_List Data View Access Rights"></a>

Get access rights to the requested data view for the calling user or client.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/accessrights
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|A list of access rights to the requested data view<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
[
  "Read",
  "Write",
  "Delete",
  "ManageAccessControl"
]
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

## Get Data View Data

<a id="opIdDataViews_Get Data View Data"></a>

Get data for the provided index parameters with paging. See documentation on paging for further information

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/data/interpolated
?startIndex={startIndex}&endIndex={endIndex}&interval={interval}&form={form}&continuationToken={continuationToken}&count={count}&cache={cache}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>`string startIndex`
<br/>The requested start index, inclusive. The default value is the ```.DefaultStartIndex``` of the data view. Optional if a default value is specified
<br/><br/>`string endIndex`
<br/>The requested end index, inclusive. The default value is the ```.DefaultEndIndex``` of the data view. Optional if a default value is specified.
<br/><br/>`string interval`
<br/>The requested interval between index values. The default value is the ```.DefaultInterval``` of the data view. Optional if a default is specified.<br/><br/><br/>`string form`
<br/>The requested data [output format](xref:DataViewsQuickStartGetData#format). Output formats: `default`, `table`, `tableh`, `csv`, `csvh`.
<br/><br/>`string continuationToken`
<br/>Used only when [paging](xref:DataViewsQuickStartGetData#paging). Not specified when requesting the first page of data.
<br/><br/>`integer count`
<br/>The requested page size. The maximum is 250,000. If the parameter is not provided, [an optimal page size will be calculated](xref:DataViewsQuickStartGetData#page-size).
<br/><br/>
`[optional] string cache`
<br/>Controls when the data view backing resources are to be refreshed. Used only when requesting the first page of data. Ignored if used with the continuationToken. Values are:

| Value | Description | 
|--|--|
| `Refresh` | Force the resource to re-resolve.  This is the default value for this API route.  
| `Preserve`| Use cached information, if available.
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Successfully retrieved data.<br/>|
|400|[ResultError](#schemaresulterror)|The request could not be understood by the server due to malformed syntax.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|https://raw.githubusercontent.com/stanasse/OCS-Docs/patch-3/content/external-references/dataviews-response-codes.yaml#404-dataviewid-standard-message|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 400 Response

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

## Get Data View Owner

<a id="opIdDataViews_Get Data View Owner"></a>

Get the owner `Trustee` of the specified data view.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[Trustee](#schematrustee)|The owner of the requested data view<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to view the requested data view's owner<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
{
    "Type": User,
    "TenantId": "55555555-5555-5555-5555-555555555555",
    "ObjectId": "44444444-4444-4444-4444-444444444444"
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

## Update Data View Owner

<a id="opIdDataViews_Update Data View Owner"></a>

Update the owner `Trustee` of the specified data view.

### Request
```text 
PUT /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/owner
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>

### Request Body

A [`Trustee`](xref:accessControl#owner)<br/>

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
|204|None|Successfully updated the data view owner<br/>|
|400|[ResultError](#schemaresulterror)|The request is not valid. See the response body for details<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized to update the requested data view's owner<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 400 Response

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

## Get Available Field Sets

<a id="opIdDataViews_Get Available Field Sets"></a>

Gets the collection of field sets that are available for use in the data view, and which are not already included in the data view.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/availablefieldsets
?cache={cache}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemsOfFieldSet](#schemaresolveditemsoffieldset)|An object with a "TimeOfResolution" and a collection of "Items", the FieldSets that resolved and which are still available<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
Content-Type: application/json  
{
  [
    {
      "Id": "demo view 1",
      ... etc.
    },
    {
      "Id": "demo view 2",
      ... etc.
    }
  ]
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

## Get Data Items by Query

<a id="opIdDataViews_Get Data Items by Query"></a>

Gets the paged collection of data items that are the results of an individual query, and which are eligible for use in the current data view. A data view has a collection of zero or more queries. Each query has an identifier. Those identifiers are used here as part of the request path.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/dataitems/{queryid}
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>`string queryId`
<br/>Query identifier<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>`[optional] integer skip`
<br/><br/>`[optional] integer count`
<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemsOfDataItem](#schemaresolveditemsofdataitem)|An object with a "TimeOfResolution" and a collection of "Items", the DataItems that resolved.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The data view or query does not exist<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of data items visible to the current user<br/>|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable<br/>|
|200|Next-Page|integer|Hyperlink to the next page of results<br/>|
|200|First-Page|integer|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
Content-Type: application/json  
{
  "TimeOfResolution": "2019-12-13T01:23:45Z",
  "Items": [
    {
      "Id": "WS_BILT",
      "Name": "WS_BILT",
      "TypeId": "quickstart-omf-weather-gen1",
      "ResourceType": "Stream",
      "Tags": [
        "Weather",
        "High Resolution",
        "Gen1"
       ],
       "Metadata": [
         {
           "Name": "Site",
           "Value": "Biltmore",
           "TypeCode": "String"
         }
       ],
       "DataItemFields": [
         {
           "Id": "Timestamp",
           "Name": "Timestamp",
           "TypeCode": "DateTime",
           "IsKey": true
         },
         {
           "Id": "SolarRadiation",
           "Name": "SolarRadiation",
           "TypeCode": "Int32",
           "IsKey": false
         },
         {
           "Id": "Temperature",
           "Name": "Temperature",
           "TypeCode": "Double",
           "IsKey": false
         }
      ],
      "IneligibleDataItemFields": []
    }
  ]
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

## Get Field Mappings

<a id="opIdDataViews_Get Field Mappings"></a>

Gets the collection of field mappings resolved for the data view. These show the exact data behind every field, for each data item, for each group.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/fieldmappings
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>`[optional] integer skip`
<br/>An optional parameter representing the zero-based offset of the first field mapping to retrieve. If not specified, a default value of 0 is used.<br/><br/><br/>`[optional] integer count`
<br/>An optional parameter representing the maximum number of field mappings to retrieve. If not specified, a default value of 100 is used.<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemsOfFieldMapping](#schemaresolveditemsoffieldmapping)|An object with a "TimeOfResolution" and a collection of "Items", the FieldMappings that resolved.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The data view or query does not exist<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of field mappings<br/>|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable<br/>|
|200|Next-Page|integer|Hyperlink to the next page of results<br/>|
|200|First-Page|integer|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
{
    "TimeOfResolution": "2019-12-13T01:23:45Z",
    "Items": [
      {
        "Id": "Timestamp",
        "Label": "Timestamp",
        "FieldKind": "IndexField",
        "TypeCode": "DateTime",
        "DataMappings": [
          {
            "TypeCode": "DateTime"
          },
          {
            "TypeCode": "DateTime"
          },
          {
            "TypeCode": "DateTime"
          }
        ]
      },
      {
        "Id": "Temperature",
        "Label": "Temperature",
        "FieldKind": "DataField",
        "TypeCode": "Double",
        "DataMappings": [
          {
            "TargetId": "WS_BILT",
            "TargetFieldKey": "Temperature",
            "TypeCode": "Double",
            "FieldSetIndex": 1,
            "FieldIndex": 0
          },
          {
            "TargetId": "WS_ROSE",
            "TargetFieldKey": "Temperature",
            "TypeCode": "Double",
            "FieldSetIndex": 1,
            "FieldIndex": 0
          },
          {
            "TargetId": "WS_WINT",
            "TargetFieldKey": "AmbientTemperature",
            "TypeCode": "Double",
            "FieldSetIndex": 1,
            "FieldIndex": 0
          }
        ]
      },
    ]
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

## Get Groups

<a id="opIdDataViews_Get Groups"></a>

Gets the collection of Groups that resolved for a data view.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/groups
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>`[optional] integer skip`
<br/>An optional parameter representing the zero-based offset of the first group to retrieve. If not specified, a default value of 0 is used.<br/><br/><br/>`[optional] integer count`
<br/>An optional parameter representing the maximum number of groups to retrieve. If not specified, a default value of 100 is used.<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemsOfGroup](#schemaresolveditemsofgroup)|An object with a "TimeOfResolution" and a collection of "Items", the Groups that resolved.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The requested data view was not found<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of groups<br/>|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable<br/>|
|200|Next-Page|integer|Hyperlink to the next page of results<br/>|
|200|First-Page|integer|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
Content-Type: application/json
{
  "TimeOfResolution": "2019-12-13T01:23:45Z",
  "Items": [
    {
      "GroupingValues": [ 
        {
          "Value": "Biltmore",
          "TypeCode": "String"
        }
      ],
      "DataItems": {
        "Query1": [
          {
            "Id": "WS_BILT",
            "Name": "WS_BILT",
            "TypeId": "quickstart-omf-weather-gen1",
            "ResourceType": "Stream",
            "Tags": [
                "Weather",
                "High Resolution",
                "Gen1"
            ],
            "Metadata": [
              {
                "Name": "Site",
                "Value": "Biltmore",
                "TypeCode": "String"
              }
            ],
            "DataItemFields": [
                {
                    "Id": "Timestamp",
                    "Name": "Timestamp",
                    "TypeCode": "DateTime",
                    "IsKey": true
                },
                {
                    "Id": "SolarRadiation",
                    "Name": "SolarRadiation",
                    "TypeCode": "Int32",
                    "IsKey": false
                },
                {
                    "Id": "Temperature",
                    "Name": "Temperature",
                    "TypeCode": "Double",
                    "IsKey": false
                }
            ],
            "IneligibleDataItemFields": []
          }
        ]
      }
    }
  ]
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

## Get Ineligible Data Items by Query

<a id="opIdDataViews_Get Ineligible Data Items by Query"></a>

Gets the paged collection of data items that are the results of an individual query, but which are not eligible for use in the current data view. A common reason for ineligibility is that the item's index property is of a different type than the data view expects. A data view has a collection of zero or more queries. Each query has an identifier. Those identifiers are used here as part of the request path.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/ineligibledataitems/{queryid}
?cache={cache}&skip={skip}&count={count}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>`string queryId`
<br/>Cancellation token<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>`[optional] integer skip`
<br/>An optional parameter representing the zero-based offset of the first data item to retrieve. If not specified, a default value of 0 is used.<br/><br/><br/>`[optional] integer count`
<br/>An optional parameter representing the maximum number of data items to retrieve. If not specified, a default value of 100 is used.<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemsOfDataItem](#schemaresolveditemsofdataitem)|An object with a "TimeOfResolution" and a collection of "Items", the DataItems that resolved.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|The data view or query does not exist<br/>|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Response Headers

|Status|Header|Type|Description|
|---|---|---|---|
|200|Total-Count|integer|The total count of data items visible to the current user<br/>|
|200|Link|integer|Hyperlinks to the first page and next page of results as applicable<br/>|
|200|Next-Page|integer|Hyperlink to the next page of results<br/>|
|200|First-Page|integer|Hyperlink to the first page of results<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
Content-Type: application/json
{
  "TimeOfResolution": "2019-12-13T01:23:45Z",
  "Items": [
    {
      "Id": "SOME_INELIGIBLE_STREAM",
      "Name": "Some Ineligible Stream",
      "TypeId": "type-with-different-index",
      "ResourceType": "Stream",
      "Tags": [],
      "Metadata": [],
      "DataItemFields": [],
      "IneligibleDataItemFields": [
         {
           "Id": "Depth",
           "Name": "Depth",
           "TypeCode": "Double",
           "IsKey": true
         },
         {
           "Id": "Density",
           "Name": "Density",
           "TypeCode": "Double",
           "IsKey": false
         }
      ]
    }
  ]
}
```
# access control responses
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

## Get Statistics

<a id="opIdDataViews_Get Statistics"></a>

Gets statistics about the size and shape on how the data view resolved.

### Request
```text 
GET /api/v1/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/resolved/statistics
?cache={cache}
```

#### Parameters

`string tenantId`
<br/>Tenant identifier<br/><br/><br/>`string namespaceId`
<br/>Namespace identifier<br/><br/><br/>`string id`
<br/>Data view identifier<br/><br/><br/>
`[optional] string cache`
<br/>"Refresh" to force the resource to re-resolve.<br/>"Preserve" to use cached information, if available. This is the default value<br/><br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ResolvedItemOfStatistics](#schemaresolveditemofstatistics)|Successfully retrieved data.<br/>|
|403|[ResultError](#schemaresulterror)|You are not authorized for this operation<br/>|
|404|[ResultError](#schemaresulterror)|https://raw.githubusercontent.com/stanasse/OCS-Docs/patch-3/content/external-references/dataviews-response-codes.yaml#404-dataviewid-standard-message|
|500|[ResultError](#schemaresulterror)|An error occurred while processing the request. See the response body for details.<br/>|

#### Example response body
> 200 Response

```json
HTTP 200 OK
{
    "TimeOfResolution": "2019-12-13T01:23:45Z",
    "DataItemCount": 24,
    "GroupCount": 2,
    "FieldMappingCount": 10,
    "DataFieldSets": [
        {
            "DataItemCount": 18,
            "UnmappedDataItemCount": 3,
            "DataFields": [
                {
                    "FieldMappingCount": 3,
                    "DataMappingCount": 6,
                    "EmptyDataMappingCount": 0,
                    "UnmappedGroupCount": 0
                },
                {
                    "FieldMappingCount": 3,
                    "DataMappingCount": 6,
                    "EmptyDataMappingCount": 2,
                    "UnmappedGroupCount": 1
                }
            ]
        },
        {
            "DataItemCount": 6,
            "UnmappedDataItemCount": 0,
            "DataFields": [
                {
                    "FieldMappingCount": 2,
                    "DataMappingCount": 4,
                    "EmptyDataMappingCount": 2,
                    "UnmappedGroupCount": 1
                }
            ]
        }
    ]
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

## ResolvedItemsOfDataItem

<a id="schemaresolveditemsofdataitem"></a>
<a id="schema_ResolvedItemsOfDataItem"></a>
<a id="tocSresolveditemsofdataitem"></a>
<a id="tocsresolveditemsofdataitem"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TimeOfResolution|date-time|false|false|None|
|Items|[[DataItem](#schemadataitem)]|false|true|None|

```json
{
  "TimeOfResolution": "2019-08-24T14:15:22Z",
  "Items": [
    {
      "Id": "string",
      "Name": "string",
      "Description": "string",
      "TypeId": "string",
      "ResourceType": 1,
      "Tags": [
        "string"
      ],
      "Metadata": [
        {
          "Name": "string",
          "Value": null,
          "Description": "string",
          "TypeCode": 0,
          "Uom": "string"
        }
      ],
      "DataItemFields": [
        {
          "Id": "string",
          "Name": "string",
          "StreamReferenceName": "string",
          "TypeCode": 0,
          "Uom": "string",
          "IsKey": true
        }
      ],
      "IneligibleDataItemFields": [
        {
          "Id": "string",
          "Name": "string",
          "StreamReferenceName": "string",
          "TypeCode": 0,
          "Uom": "string",
          "IsKey": true
        }
      ]
    }
  ]
}

```

---

## DataItem

<a id="schemadataitem"></a>
<a id="schema_DataItem"></a>
<a id="tocSdataitem"></a>
<a id="tocsdataitem"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|TypeId|string|false|true|None|
|ResourceType|[DataItemResourceType](#schemadataitemresourcetype)|false|false|None|
|Tags|string[]|false|true|None|
|Metadata|[[MetadataValueOfObject](#schemametadatavalueofobject)]|false|true|None|
|DataItemFields|[[DataItemField](#schemadataitemfield)]|false|true|None|
|IneligibleDataItemFields|[[DataItemField](#schemadataitemfield)]|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TypeId": "string",
  "ResourceType": 1,
  "Tags": [
    "string"
  ],
  "Metadata": [
    {
      "Name": "string",
      "Value": null,
      "Description": "string",
      "TypeCode": 0,
      "Uom": "string"
    }
  ],
  "DataItemFields": [
    {
      "Id": "string",
      "Name": "string",
      "StreamReferenceName": "string",
      "TypeCode": 0,
      "Uom": "string",
      "IsKey": true
    }
  ],
  "IneligibleDataItemFields": [
    {
      "Id": "string",
      "Name": "string",
      "StreamReferenceName": "string",
      "TypeCode": 0,
      "Uom": "string",
      "IsKey": true
    }
  ]
}

```

---

## MetadataValueOfObject

<a id="schemametadatavalueofobject"></a>
<a id="schema_MetadataValueOfObject"></a>
<a id="tocSmetadatavalueofobject"></a>
<a id="tocsmetadatavalueofobject"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Name|string|false|true|None|
|Value|any|false|true|None|
|Description|string|false|true|None|
|TypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Uom|string|false|true|None|

```json
{
  "Name": "string",
  "Value": null,
  "Description": "string",
  "TypeCode": 0,
  "Uom": "string"
}

```

---

## DataItemField

<a id="schemadataitemfield"></a>
<a id="schema_DataItemField"></a>
<a id="tocSdataitemfield"></a>
<a id="tocsdataitemfield"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|StreamReferenceName|string|false|true|None|
|TypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Uom|string|false|true|None|
|IsKey|boolean|false|false|None|

```json
{
  "Id": "string",
  "Name": "string",
  "StreamReferenceName": "string",
  "TypeCode": 0,
  "Uom": "string",
  "IsKey": true
}

```

---

## ResolvedItemsOfGroup

<a id="schemaresolveditemsofgroup"></a>
<a id="schema_ResolvedItemsOfGroup"></a>
<a id="tocSresolveditemsofgroup"></a>
<a id="tocsresolveditemsofgroup"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TimeOfResolution|date-time|false|false|None|
|Items|[[Group](#schemagroup)]|false|true|None|

```json
{
  "TimeOfResolution": "2019-08-24T14:15:22Z",
  "Items": [
    {
      "GroupingValues": [
        {
          "Value": null,
          "TypeCode": 0,
          "Uom": "string"
        }
      ],
      "DataItems": {
        "property1": [
          {
            "Id": "string",
            "Name": "string",
            "Description": "string",
            "TypeId": "string",
            "ResourceType": "[",
            "Tags": [
              null
            ],
            "Metadata": [
              null
            ],
            "DataItemFields": [
              null
            ],
            "IneligibleDataItemFields": [
              null
            ]
          }
        ],
        "property2": [
          {
            "Id": "string",
            "Name": "string",
            "Description": "string",
            "TypeId": "string",
            "ResourceType": "[",
            "Tags": [
              null
            ],
            "Metadata": [
              null
            ],
            "DataItemFields": [
              null
            ],
            "IneligibleDataItemFields": [
              null
            ]
          }
        ]
      }
    }
  ]
}

```

---

## Group

<a id="schemagroup"></a>
<a id="schema_Group"></a>
<a id="tocSgroup"></a>
<a id="tocsgroup"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|GroupingValues|[[GroupingValueOfObject](#schemagroupingvalueofobject)]|false|true|None|
|DataItems|object|false|true|None|

```json
{
  "GroupingValues": [
    {
      "Value": null,
      "TypeCode": 0,
      "Uom": "string"
    }
  ],
  "DataItems": {
    "property1": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "TypeId": "string",
        "ResourceType": 1,
        "Tags": [
          "string"
        ],
        "Metadata": [
          {
            "Name": "string",
            "Value": null,
            "Description": "string",
            "TypeCode": "[",
            "Uom": "string"
          }
        ],
        "DataItemFields": [
          {
            "Id": "string",
            "Name": "string",
            "StreamReferenceName": "string",
            "TypeCode": "[",
            "Uom": "string",
            "IsKey": true
          }
        ],
        "IneligibleDataItemFields": [
          {
            "Id": "string",
            "Name": "string",
            "StreamReferenceName": "string",
            "TypeCode": "[",
            "Uom": "string",
            "IsKey": true
          }
        ]
      }
    ],
    "property2": [
      {
        "Id": "string",
        "Name": "string",
        "Description": "string",
        "TypeId": "string",
        "ResourceType": 1,
        "Tags": [
          "string"
        ],
        "Metadata": [
          {
            "Name": "string",
            "Value": null,
            "Description": "string",
            "TypeCode": "[",
            "Uom": "string"
          }
        ],
        "DataItemFields": [
          {
            "Id": "string",
            "Name": "string",
            "StreamReferenceName": "string",
            "TypeCode": "[",
            "Uom": "string",
            "IsKey": true
          }
        ],
        "IneligibleDataItemFields": [
          {
            "Id": "string",
            "Name": "string",
            "StreamReferenceName": "string",
            "TypeCode": "[",
            "Uom": "string",
            "IsKey": true
          }
        ]
      }
    ]
  }
}

```

---

## GroupingValueOfObject

<a id="schemagroupingvalueofobject"></a>
<a id="schema_GroupingValueOfObject"></a>
<a id="tocSgroupingvalueofobject"></a>
<a id="tocsgroupingvalueofobject"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Value|any|false|true|None|
|TypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Uom|string|false|true|None|

```json
{
  "Value": null,
  "TypeCode": 0,
  "Uom": "string"
}

```

---

## DataItemOfObject

<a id="schemadataitemofobject"></a>
<a id="schema_DataItemOfObject"></a>
<a id="tocSdataitemofobject"></a>
<a id="tocsdataitemofobject"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Name|string|false|true|None|
|Description|string|false|true|None|
|TypeId|string|false|true|None|
|ResourceType|[DataItemResourceType](#schemadataitemresourcetype)|false|false|None|
|Tags|string[]|false|true|None|
|Metadata|[[MetadataValueOfObject](#schemametadatavalueofobject)]|false|true|None|
|DataItemFields|[[DataItemField](#schemadataitemfield)]|false|true|None|
|IneligibleDataItemFields|[[DataItemField](#schemadataitemfield)]|false|true|None|

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "TypeId": "string",
  "ResourceType": 1,
  "Tags": [
    "string"
  ],
  "Metadata": [
    {
      "Name": "string",
      "Value": null,
      "Description": "string",
      "TypeCode": 0,
      "Uom": "string"
    }
  ],
  "DataItemFields": [
    {
      "Id": "string",
      "Name": "string",
      "StreamReferenceName": "string",
      "TypeCode": 0,
      "Uom": "string",
      "IsKey": true
    }
  ],
  "IneligibleDataItemFields": [
    {
      "Id": "string",
      "Name": "string",
      "StreamReferenceName": "string",
      "TypeCode": 0,
      "Uom": "string",
      "IsKey": true
    }
  ]
}

```

---

## ResolvedItemsOfFieldMapping

<a id="schemaresolveditemsoffieldmapping"></a>
<a id="schema_ResolvedItemsOfFieldMapping"></a>
<a id="tocSresolveditemsoffieldmapping"></a>
<a id="tocsresolveditemsoffieldmapping"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TimeOfResolution|date-time|false|false|None|
|Items|[[FieldMapping](#schemafieldmapping)]|false|true|None|

```json
{
  "TimeOfResolution": "2019-08-24T14:15:22Z",
  "Items": [
    {
      "Id": "string",
      "Label": "string",
      "FieldKind": 1,
      "TypeCode": 0,
      "Uom": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "DataMappings": [
        {
          "TargetId": "string",
          "TargetStreamReferenceName": "string",
          "TargetFieldKey": "string",
          "TypeCode": 0,
          "Uom": "string",
          "SummaryType": 0,
          "SummaryDirection": null,
          "FieldSetIndex": 0,
          "FieldIndex": 0
        }
      ]
    }
  ]
}

```

---

## FieldMapping

<a id="schemafieldmapping"></a>
<a id="schema_FieldMapping"></a>
<a id="tocSfieldmapping"></a>
<a id="tocsfieldmapping"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|Id|string|false|true|None|
|Label|string|false|true|None|
|FieldKind|[FieldKind](#schemafieldkind)|false|false|None|
|TypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Uom|string|false|true|None|
|SummaryType|[SdsSummaryType](#schemasdssummarytype)|false|true|None|
|SummaryDirection|[SummaryDirection](#schemasummarydirection)|false|true|None|
|DataMappings|[[DataMapping](#schemadatamapping)]|false|true|None|

```json
{
  "Id": "string",
  "Label": "string",
  "FieldKind": 1,
  "TypeCode": 0,
  "Uom": "string",
  "SummaryType": 0,
  "SummaryDirection": 1,
  "DataMappings": [
    {
      "TargetId": "string",
      "TargetStreamReferenceName": "string",
      "TargetFieldKey": "string",
      "TypeCode": 0,
      "Uom": "string",
      "SummaryType": 0,
      "SummaryDirection": 1,
      "FieldSetIndex": 0,
      "FieldIndex": 0
    }
  ]
}

```

---

## FieldKind

<a id="schemafieldkind"></a>
<a id="schema_FieldKind"></a>
<a id="tocSfieldkind"></a>
<a id="tocsfieldkind"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|IndexField|1|
|GroupingField|2|
|DataField|3|
|FieldId|4|
|FieldUom|5|

---

## DataMapping

<a id="schemadatamapping"></a>
<a id="schema_DataMapping"></a>
<a id="tocSdatamapping"></a>
<a id="tocsdatamapping"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TargetId|string|false|true|None|
|TargetStreamReferenceName|string|false|true|None|
|TargetFieldKey|string|false|true|None|
|TypeCode|[SdsTypeCode](#schemasdstypecode)|false|false|None|
|Uom|string|false|true|None|
|SummaryType|[SdsSummaryType](#schemasdssummarytype)|false|false|None|
|SummaryDirection|[SummaryDirection](#schemasummarydirection)|false|true|None|
|FieldSetIndex|int32|false|true|None|
|FieldIndex|int32|false|true|None|

```json
{
  "TargetId": "string",
  "TargetStreamReferenceName": "string",
  "TargetFieldKey": "string",
  "TypeCode": 0,
  "Uom": "string",
  "SummaryType": 0,
  "SummaryDirection": 1,
  "FieldSetIndex": 0,
  "FieldIndex": 0
}

```

---

## ResolvedItemsOfFieldSet

<a id="schemaresolveditemsoffieldset"></a>
<a id="schema_ResolvedItemsOfFieldSet"></a>
<a id="tocSresolveditemsoffieldset"></a>
<a id="tocsresolveditemsoffieldset"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TimeOfResolution|date-time|false|false|None|
|Items|[[FieldSet](#schemafieldset)]|false|true|None|

```json
{
  "TimeOfResolution": "2019-08-24T14:15:22Z",
  "Items": [
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
  ]
}

```

---

## ResolvedItemOfStatistics

<a id="schemaresolveditemofstatistics"></a>
<a id="schema_ResolvedItemOfStatistics"></a>
<a id="tocSresolveditemofstatistics"></a>
<a id="tocsresolveditemofstatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|TimeOfResolution|date-time|false|false|None|
|Item|[Statistics](#schemastatistics)|false|true|None|

```json
{
  "TimeOfResolution": "2019-08-24T14:15:22Z",
  "Item": {
    "DataItemCount": 0,
    "GroupCount": 0,
    "FieldMappingCount": 0,
    "Queries": [
      {
        "QueryId": "string",
        "DataItemCount": 0,
        "DataItemWithIneligibleFieldsCount": 0,
        "IneligibleDataItemCount": 0
      }
    ],
    "DataFieldSets": [
      {
        "DataItemCount": 0,
        "UnmappedDataItemCount": 0,
        "DataFields": [
          null
        ]
      }
    ]
  }
}

```

---

## Statistics

<a id="schemastatistics"></a>
<a id="schema_Statistics"></a>
<a id="tocSstatistics"></a>
<a id="tocsstatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|DataItemCount|int32|false|false|None|
|GroupCount|int32|false|false|None|
|FieldMappingCount|int32|false|false|None|
|Queries|[[QueryStatistics](#schemaquerystatistics)]|false|true|None|
|DataFieldSets|[[DataFieldSetStatistics](#schemadatafieldsetstatistics)]|false|true|None|

```json
{
  "DataItemCount": 0,
  "GroupCount": 0,
  "FieldMappingCount": 0,
  "Queries": [
    {
      "QueryId": "string",
      "DataItemCount": 0,
      "DataItemWithIneligibleFieldsCount": 0,
      "IneligibleDataItemCount": 0
    }
  ],
  "DataFieldSets": [
    {
      "DataItemCount": 0,
      "UnmappedDataItemCount": 0,
      "DataFields": [
        {
          "FieldMappingCount": 0,
          "DataMappingCount": 0,
          "EmptyDataMappingCount": 0,
          "UnmappedGroupCount": 0
        }
      ]
    }
  ]
}

```

---

## QueryStatistics

<a id="schemaquerystatistics"></a>
<a id="schema_QueryStatistics"></a>
<a id="tocSquerystatistics"></a>
<a id="tocsquerystatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|QueryId|string|false|true|None|
|DataItemCount|int32|false|false|None|
|DataItemWithIneligibleFieldsCount|int32|false|false|None|
|IneligibleDataItemCount|int32|false|false|None|

```json
{
  "QueryId": "string",
  "DataItemCount": 0,
  "DataItemWithIneligibleFieldsCount": 0,
  "IneligibleDataItemCount": 0
}

```

---

## DataFieldSetStatistics

<a id="schemadatafieldsetstatistics"></a>
<a id="schema_DataFieldSetStatistics"></a>
<a id="tocSdatafieldsetstatistics"></a>
<a id="tocsdatafieldsetstatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|DataItemCount|int32|false|false|None|
|UnmappedDataItemCount|int32|false|false|None|
|DataFields|[[DataFieldStatistics](#schemadatafieldstatistics)]|false|true|None|

```json
{
  "DataItemCount": 0,
  "UnmappedDataItemCount": 0,
  "DataFields": [
    {
      "FieldMappingCount": 0,
      "DataMappingCount": 0,
      "EmptyDataMappingCount": 0,
      "UnmappedGroupCount": 0
    }
  ]
}

```

---

## DataFieldStatistics

<a id="schemadatafieldstatistics"></a>
<a id="schema_DataFieldStatistics"></a>
<a id="tocSdatafieldstatistics"></a>
<a id="tocsdatafieldstatistics"></a>

### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|FieldMappingCount|int32|false|false|None|
|DataMappingCount|int32|false|false|None|
|EmptyDataMappingCount|int32|false|false|None|
|UnmappedGroupCount|int32|false|false|None|

```json
{
  "FieldMappingCount": 0,
  "DataMappingCount": 0,
  "EmptyDataMappingCount": 0,
  "UnmappedGroupCount": 0
}

```

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

