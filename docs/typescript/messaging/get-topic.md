# getTopic

Description: Get a topic by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topicId` | `string` | ✅ | Topic ID. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Topic = await messaging.getTopic({
  topicId: '<TOPIC_ID>',
});
```

## Response Model

Returns a `Models.Topic` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Topic ID. |
| `createdAt` | `string` | Topic creation time in ISO 8601 format. |
| `updatedAt` | `string` | Topic update date in ISO 8601 format. |
| `name` | `string` | The name of the topic. |
| `emailTotal` | `number` | Total count of email subscribers subscribed to the topic. |
| `smsTotal` | `number` | Total count of SMS subscribers subscribed to the topic. |
| `pushTotal` | `number` | Total count of push subscribers subscribed to the topic. |
| `subscribe` | `string[]` | Subscribe permissions. |
