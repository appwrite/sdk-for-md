# deleteSubscriber

Description: Delete a subscriber by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `topicId` | `string` | ✅ | Topic ID. The topic ID subscribed to. |
| `subscriberId` | `string` | ✅ | Subscriber ID. |

## Usage

```typescript
import { Client, Messaging } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result = await messaging.deleteSubscriber({
  topicId: '<TOPIC_ID>',
  subscriberId: '<SUBSCRIBER_ID>',
});
```
