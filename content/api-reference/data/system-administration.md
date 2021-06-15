---
uid: ""

---

# System Administration

## `Execute Callback Function`

<a id="opIdSystemAdministration_Execute Callback Function"></a>

Execute the callback function specified by the function against the component specified by the component ID.

### Request
```text 
POST /api/v1/Administration/{componentId}/{function}
```

#### Parameters

`string componentId`
<br/>The component ID.<br/><br/>`string function`
<br/>The name of the callback function to execute.<br/><br/>

### Response

|Status Code|Body Type|Description|
|---|---|---|
|204|None|The result of the action.|
|404|None|The specified function name or component is not found.|

