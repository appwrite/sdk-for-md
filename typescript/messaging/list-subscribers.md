# listSubscribers

Description: Get a list of all subscribers from the current Appwrite project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topicId` | `string` | ✅ | Topic ID. The topic ID subscribed to. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: name, provider, type, enabled (Default: `[]`) |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.SubscriberList = await messaging.listSubscribers({
  topicId: '<TOPIC_ID>',
  queries: [],
  search: '<SEARCH>',
  total: false,
});
```

## Response Model

Returns a `Models.SubscriberList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of subscribers that matched your query. |
| `subscribers` | `object[]` | List of subscribers. |
