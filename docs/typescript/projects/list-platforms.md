# listPlatforms

Description: Get a list of all platforms in the project. This endpoint returns an array of all platforms and their configurations.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.PlatformList = await projects.listPlatforms({
  projectId: '<PROJECT_ID>',
  total: false,
});
```

## Response Model

Returns a `Models.PlatformList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of platforms that matched your query. |
| `platforms` | `object[]` | List of platforms. |
