# list

Description: Get a list of all webhooks belonging to the project. You can use the query params to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: name, url, httpUser, security, events, enabled, logs, attempts (Default: `[]`) |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Webhooks, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const webhooks = new Webhooks(client);
const result: Models.WebhookList = await webhooks.list({
  queries: [],
  total: false,
});
```

## Response Model

Returns a `Models.WebhookList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of webhooks that matched your query. |
| `webhooks` | `object[]` | List of webhooks. |
