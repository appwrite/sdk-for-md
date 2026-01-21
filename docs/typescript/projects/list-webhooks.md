# listWebhooks

Description: Get a list of all webhooks belonging to the project. You can use the query params to filter your results.

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
const result: Models.WebhookList = await projects.listWebhooks({
  projectId: '<PROJECT_ID>',
  total: false,
});
```

## Response Model

Returns a `Models.WebhookList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of webhooks that matched your query. |
| `webhooks` | `object[]` | List of webhooks. |
