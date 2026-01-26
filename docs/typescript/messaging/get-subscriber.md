# getSubscriber

Description: Get a subscriber by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topicId` | `string` | ✅ | Topic ID. The topic ID subscribed to. |
| `subscriberId` | `string` | ✅ | Subscriber ID. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Subscriber = await messaging.getSubscriber({
  topicId: '<TOPIC_ID>',
  subscriberId: '<SUBSCRIBER_ID>',
});
```

## Response Model

Returns a `Models.Subscriber` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Subscriber ID. |
| `createdAt` | `string` | Subscriber creation time in ISO 8601 format. |
| `updatedAt` | `string` | Subscriber update date in ISO 8601 format. |
| `targetId` | `string` | Target ID. |
| `target` | `object` | Target. |
| `userId` | `string` | Topic ID. |
| `userName` | `string` | User Name. |
| `topicId` | `string` | Topic ID. |
| `providerType` | `string` | The target provider type. Can be one of the following: `email`, `sms` or `push`. |
