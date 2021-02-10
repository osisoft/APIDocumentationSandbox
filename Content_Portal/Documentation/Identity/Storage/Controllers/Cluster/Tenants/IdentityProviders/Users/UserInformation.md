

<h1 id="identity-storage-controllers-cluster-tenants-identityproviders-users-userinformation-userinformation">UserInformation</h1>

## GetUserInformationForAuthentication

<a id="opIdUserInformation_GetUserInformationForAuthentication"></a>

Get UserInformation for Authentication.

### Request
```text 
GET /api/v1/tenants/{tenantId}/identityproviders/{identityProviderId}/users/{identityProviderSpecificUserId}/UserInformation
```

<h3 id="userinformation_getuserinformationforauthentication-parameters">Parameters</h3>

`string tenantId`<br/>Id of Tenant.<br/><br/>`string identityProviderId`<br/>Identity Provider Id.<br/><br/>`string identityProviderSpecificUserId`<br/>Identity Provider Specific User Id. Ex. ExternalUserId for AD, ObjectId for AAD.<br/><br/>`string claimTypes`<br/>Claim Types.<br/><br/>

<h3 id="userinformation_getuserinformationforauthentication-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserInformationResponse](#schemauserinformationresponse)|UserInformation or UserInformationMultiStatusResponse.|
|207|[UserInformationMultiStatusResponse](#schemauserinformationmultistatusresponse)|UserInformation or UserInformationMultiStatusResponse.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "UserInformation": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}
```

> 400 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 403 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 404 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 500 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

### Authorization

To perform this operation, you must have one of the following roles: <br/><br/>
<b>Authorized Roles</b> 
<ul>
<li>Account Administrator</li>
</ul>

# Schemas

<h2 id="tocS_UserInformationResponse">UserInformationResponse</h2>

<a id="schemauserinformationresponse"></a>
<a id="schema_UserInformationResponse"></a>
<a id="tocSuserinformationresponse"></a>
<a id="tocsuserinformationresponse"></a>

```json
{
  "UserInformation": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|UserInformation|object|false|true|None|

<h2 id="tocS_UserInformationMultiStatusResponse">UserInformationMultiStatusResponse</h2>

<a id="schemauserinformationmultistatusresponse"></a>
<a id="schema_UserInformationMultiStatusResponse"></a>
<a id="tocSuserinformationmultistatusresponse"></a>
<a id="tocsuserinformationmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "string",
      "Error": "string",
      "Reason": "string",
      "Resolution": "string",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": {
    "UserInformation": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  }
}

```

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|false|true|None|
|Error|string|false|true|None|
|Reason|string|false|true|None|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]|false|true|[ChildError objects returned in a 207 response.]|
|Data|[UserInformationResponse](#schemauserinformationresponse)|false|true|None|

<h2 id="tocS_MultiStatusResponseChildError">MultiStatusResponseChildError</h2>

<a id="schemamultistatusresponsechilderror"></a>
<a id="schema_MultiStatusResponseChildError"></a>
<a id="tocSmultistatusresponsechilderror"></a>
<a id="tocsmultistatusresponsechilderror"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "Resolution": "string",
  "StatusCode": 0,
  "ModelId": "string",
  "property1": null,
  "property2": null
}

```

ChildError objects returned in a 207 response.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|
|StatusCode|int32|false|false|Gets or sets hTTP status code.|
|ModelId|string|false|true|Gets or sets model ID.|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}

```

Object returned whenever there is an error.

### Properties

|Name|Type|Required|Nullable|Description|
|---|---|---|---|---|
|OperationId|string|true|false|Gets or sets operationId of action that caused the Error.|
|Error|string|true|false|Gets or sets error description.|
|Reason|string|true|false|Gets or sets reason for the Error.|
|Resolution|string|true|false|Gets or sets what can be done to resolve the Error.|

