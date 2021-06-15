---
uid: ""

---

# System Configuration

## `Get All Configurations`

<a id="opIdSystemConfiguration_Get All Configurations"></a>

TODO

### Request
```text 
GET /api/v1/Configuration
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Put Edge System Configurations`

<a id="opIdSystemConfiguration_Put Edge System Configurations"></a>

TODO

### Request
```text 
PUT /api/v1/Configuration
```

#### Parameters

`[optional] [JsonValueKind](#schemajsonvaluekind) ValueKind`
<br/><br/>

#### Enumerated Values

|Parameter|Value|
|---|---|
|ValueKind|0|
|ValueKind|1|
|ValueKind|2|
|ValueKind|3|
|ValueKind|4|
|ValueKind|5|
|ValueKind|6|
|ValueKind|7|

### Request Body

TODO<br/>

```json
{
  "property1": {
    "property1": {
      "ValueKind": 0
    },
    "property2": {
      "ValueKind": 0
    }
  },
  "property2": {
    "property1": {
      "ValueKind": 0
    },
    "property2": {
      "ValueKind": 0
    }
  }
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Component Configurations`

<a id="opIdSystemConfiguration_Get Component Configurations"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Configuration`

<a id="opIdSystemConfiguration_Get Configuration"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/{facet}
?diff={diff}&skip={skip}&count={count}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>`string diff`
<br/>TODO<br/><br/>`integer skip`
<br/>TODO<br/><br/>`integer count`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Post Configuration`

<a id="opIdSystemConfiguration_Post Configuration"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/{facet}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Put Configuration`

<a id="opIdSystemConfiguration_Put Configuration"></a>

TODO

### Request
```text 
PUT /api/v1/Configuration/{componentId}/{facet}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Patch Configuration`

<a id="opIdSystemConfiguration_Patch Configuration"></a>

TODO

### Request
```text 
PATCH /api/v1/Configuration/{componentId}/{facet}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete Configuration`

<a id="opIdSystemConfiguration_Delete Configuration"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/{facet}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Configuration By Id`

<a id="opIdSystemConfiguration_Get Configuration By Id"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/{facet}/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Put Configuration (id path)`

<a id="opIdSystemConfiguration_Put Configuration (id path)"></a>

TODO

### Request
```text 
PUT /api/v1/Configuration/{componentId}/{facet}/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Patch Configuration Entry`

<a id="opIdSystemConfiguration_Patch Configuration Entry"></a>

TODO

### Request
```text 
PATCH /api/v1/Configuration/{componentId}/{facet}/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete Configuration (id path)`

<a id="opIdSystemConfiguration_Delete Configuration (id path)"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/{facet}/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string facet`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Data Selection Operation`

<a id="opIdSystemConfiguration_Data Selection Operation"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/dataSelection/{operation}
?discoveryId={discoveryId}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string operation`
<br/>TODO<br/><br/>`string discoveryId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Discovery States`

<a id="opIdSystemConfiguration_Get Discovery States"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/discoveries
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Start Discovery`

<a id="opIdSystemConfiguration_Start Discovery"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/discoveries
?scheduleId={scheduleId}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string scheduleId`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete Discoveries`

<a id="opIdSystemConfiguration_Delete Discoveries"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/discoveries
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Discovery State By Id`

<a id="opIdSystemConfiguration_Get Discovery State By Id"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/discoveries/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete Discovery`

<a id="opIdSystemConfiguration_Delete Discovery"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/discoveries/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Cancel Discovery`

<a id="opIdSystemConfiguration_Cancel Discovery"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/discoveries/{id}/cancel
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get Discovery Result By Id`

<a id="opIdSystemConfiguration_Get Discovery Result By Id"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/discoveries/{id}/result
?diff={diff}&count={count}&skip={skip}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>`string diff`
<br/>TODO<br/><br/>`integer count`
<br/>TODO<br/><br/>`integer skip`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete Discovery Result`

<a id="opIdSystemConfiguration_Delete Discovery Result"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/discoveries/{id}/result
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get History Recovery States`

<a id="opIdSystemConfiguration_Get History Recovery States"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/historyRecoveries
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Start On Demand History Recovery`

<a id="opIdSystemConfiguration_Start On Demand History Recovery"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/historyRecoveries
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Request Body

TODO<br/>

```json
{
  "ValueKind": 0
}
```

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete History Recoveries`

<a id="opIdSystemConfiguration_Delete History Recoveries"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/historyRecoveries
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Get History Recovery State By Id`

<a id="opIdSystemConfiguration_Get History Recovery State By Id"></a>

TODO

### Request
```text 
GET /api/v1/Configuration/{componentId}/historyRecoveries/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Delete History Recovery`

<a id="opIdSystemConfiguration_Delete History Recovery"></a>

TODO

### Request
```text 
DELETE /api/v1/Configuration/{componentId}/historyRecoveries/{id}
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Cancel History Recovery`

<a id="opIdSystemConfiguration_Cancel History Recovery"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/historyRecoveries/{id}/cancel
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---

## `Resume History Recovery`

<a id="opIdSystemConfiguration_Resume History Recovery"></a>

TODO

### Request
```text 
POST /api/v1/Configuration/{componentId}/historyRecoveries/{id}/resume
```

#### Parameters

`string componentId`
<br/>TODO<br/><br/>`string id`
<br/>TODO<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|200|string|TODO|

---
## Definitions

### JsonElement

<a id="schemajsonelement"></a>
<a id="schema_JsonElement"></a>
<a id="tocSjsonelement"></a>
<a id="tocsjsonelement"></a>

#### Properties

|Property Name|Data Type|Required|Nullable|Description|
|---|---|---|---|---|
|ValueKind|[JsonValueKind](#schemajsonvaluekind)|false|false|None|

```json
{
  "ValueKind": 0
}

```

---

### JsonValueKind

<a id="schemajsonvaluekind"></a>
<a id="schema_JsonValueKind"></a>
<a id="tocSjsonvaluekind"></a>
<a id="tocsjsonvaluekind"></a>

#### Enumerated Values

|Property|Value|
|---|---|
|Undefined|0|
|Object|1|
|Array|2|
|String|3|
|Number|4|
|True|5|
|False|6|
|Null|7|

---

