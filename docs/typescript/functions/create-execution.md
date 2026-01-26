# createExecution

Description: Trigger a function execution. The returned object will return you the current execution status. You can ping the `Get Execution` endpoint to get updates on the current execution status. Once this endpoint is called, your function execution process will start asynchronously.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `body` | `string` | ❌ | HTTP body of execution. Default value is empty string. |
| `async` | `boolean` | ❌ | Execute code in the background. Default value is false. |
| `path` | `string` | ❌ | HTTP path of execution. Path can include query params. Default value is / (Default: `/`) |
| `method` | `ExecutionMethod` | ❌ | HTTP method of execution. Default value is POST. (Default: `POST`)<br>**Allowed:** `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `OPTIONS`, `HEAD` |
| `headers` | `object` | ❌ | HTTP headers of execution. Defaults to empty. (Default: `{}`) |
| `scheduledAt` | `string` | ❌ | Scheduled execution time in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. DateTime value must be in future with precision in minutes. |

## Usage

```typescript
import { Client, Functions, ExecutionMethod, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Execution = await functions.createExecution({
  functionId: '<FUNCTION_ID>',
  body: '<BODY>',
  async: false,
  path: '<PATH>',
  method: ExecutionMethod.GET,
  headers: {},
  scheduledAt: '<SCHEDULED_AT>',
});
```

## Response Model

Returns a `Models.Execution` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Execution ID. |
| `createdAt` | `string` | Execution creation date in ISO 8601 format. |
| `updatedAt` | `string` | Execution update date in ISO 8601 format. |
| `permissions` | `string[]` | Execution roles. |
| `functionId` | `string` | Function ID. |
| `deploymentId` | `string` | Function&#039;s deployment ID used to create the execution. |
| `trigger` | `ExecutionTrigger` | The trigger that caused the function to execute. Possible values can be: `http`, `schedule`, or `event`. |
| `status` | `ExecutionStatus` | The status of the function execution. Possible values can be: `waiting`, `processing`, `completed`, `failed`, or `scheduled`. |
| `requestMethod` | `string` | HTTP request method type. |
| `requestPath` | `string` | HTTP request path and query. |
| `requestHeaders` | `object[]` | HTTP request headers as a key-value object. This will return only whitelisted headers. All headers are returned if execution is created as synchronous. |
| `responseStatusCode` | `number` | HTTP response status code. |
| `responseBody` | `string` | HTTP response body. This will return empty unless execution is created as synchronous. |
| `responseHeaders` | `object[]` | HTTP response headers as a key-value object. This will return only whitelisted headers. All headers are returned if execution is created as synchronous. |
| `logs` | `string` | Function logs. Includes the last 4,000 characters. This will return an empty string unless the response is returned using an API key or as part of a webhook payload. |
| `errors` | `string` | Function errors. Includes the last 4,000 characters. This will return an empty string unless the response is returned using an API key or as part of a webhook payload. |
| `duration` | `number` | Resource(function/site) execution duration in seconds. |
| `scheduledAt` | `string` | The scheduled time for execution. If left empty, execution will be queued immediately. |
