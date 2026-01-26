# getLog

Description: Get a site request log by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `logId` | `string` | ✅ | Log ID. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Execution = await sites.getLog({
  siteId: '<SITE_ID>',
  logId: '<LOG_ID>',
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
