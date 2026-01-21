# delete

Description: Delete a message. If the message is not a draft or scheduled, but has been sent, this will not recall the message.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `messageId` | `string` | ✅ | Message ID. |

## Usage

```typescript
import { Client, Messaging } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result = await messaging.delete({
  messageId: '<MESSAGE_ID>',
});
```
