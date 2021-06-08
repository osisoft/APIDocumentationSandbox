---
uid: ""

---

# Service Blog
API's for CRUD operations on the Service Blog.

## `List By Page`

<a id="opIdServiceBlog_List By Page"></a>

Returns blog entries ordered by time posted.

### Request
```text 
GET /api/v1/ServiceBlog/Entries
?skip={skip}&count={count}&includeDeleted={includeDeleted}
```

#### Parameters

`[optional] integer skip`
<br/>Number of blogs to skip for paging purposes.<br/><br/>`[optional] integer count`
<br/>Number of blogs to count after skip for paging purposes.<br/><br/>`[optional] boolean includeDeleted`
<br/>Whether deleted entries are included in return.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ServiceBlogEntry](#schemaserviceblogentry)[]|An array of `ServiceBlogEntry` objects.|

#### Example response body
> 200 Response

```json
[
  {
    "IsDeleted": true,
    "Id": 0,
    "TimePosted": "2019-08-24T14:15:22Z",
    "Title": "string",
    "Content": "string",
    "Author": "string"
  }
]
```

---

## `Get Entry By Id`

<a id="opIdServiceBlog_Get Entry By Id"></a>

Returns a blog entry specified by ID.

### Request
```text 
GET /api/v1/ServiceBlog/Entries/{id}
```

#### Parameters

`string id`
<br/>Identifier of the blog entry to retrieve.<br/><br/>

#### Request Headers

|Header|Type|Required|Description|
|---|---|---|---|

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|[ServiceBlogEntry](#schemaserviceblogentry)|The `ServiceBlogEntry` with Id `id`.|

#### Example response body
> 200 Response

```json
{
  "IsDeleted": true,
  "Id": 0,
  "TimePosted": "2019-08-24T14:15:22Z",
  "Title": "string",
  "Content": "string",
  "Author": "string"
}
```

---
## Definitions

### ServiceBlogEntry

<a id="schemaserviceblogentry"></a>
<a id="schema_ServiceBlogEntry"></a>
<a id="tocSserviceblogentry"></a>
<a id="tocsserviceblogentry"></a>

Representation of a server-side database interpretation of a Blog.

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|IsDeleted|boolean|false|false|Gets or sets a value indicating whether boolean flag that represents the Blog Entry's soft delete status. True = Deleted, False = Not Deleted.|
|Id|int32|false|false|Gets or sets the identifier for the blog entry.|
|TimePosted|date-time|false|false|Gets or sets this is a recorded timestamp managed by the blog editor. Not related the the TableEntity timestamp.|
|Title|string|false|true|Gets or sets title of the blog entry.|
|Content|string|false|true|Gets or sets the content body of the blog entry. This is where the details of the blog entry are located.|
|Author|string|false|true|Gets or sets the Author is who intially created the blog entry.|

```json
{
  "IsDeleted": true,
  "Id": 0,
  "TimePosted": "2019-08-24T14:15:22Z",
  "Title": "string",
  "Content": "string",
  "Author": "string"
}

```

---

