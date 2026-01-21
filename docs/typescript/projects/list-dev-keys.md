# listDevKeys

Description: List all the project\&#039;s dev keys. Dev keys are project specific and allow you to bypass rate limits and get better error logging during development.&#039;

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: accessedAt, expire (Default: `[]`) |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.DevKeyList = await projects.listDevKeys({
  projectId: '<PROJECT_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.DevKeyList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of devKeys that matched your query. |
| `devKeys` | `object[]` | List of devKeys. |
