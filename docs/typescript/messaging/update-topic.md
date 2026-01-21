# updateTopic

Description: Update a topic by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topicId` | `string` | ✅ | Topic ID. |
| `name` | `string` | ❌ | Topic Name. |
| `subscribe` | `string[]` | ❌ | An array of role strings with subscribe permission. By default all users are granted with any subscribe permission. [learn more about roles](https://appwrite.io/docs/permissions#permission-roles). Maximum of 100 roles are allowed, each 64 characters long. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Topic = await messaging.updateTopic({
  topicId: '<TOPIC_ID>',
  name: '<NAME>',
  subscribe: ["any"],
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
