# getMessage

Description: Get a message by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `messageId` | `string` | ✅ | Message ID. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Message = await messaging.getMessage({
  messageId: '<MESSAGE_ID>',
});
```

## Response Model

Returns a `Models.Message` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Message ID. |
| `createdAt` | `string` | Message creation time in ISO 8601 format. |
| `updatedAt` | `string` | Message update date in ISO 8601 format. |
| `providerType` | `string` | Message provider type. |
| `topics` | `string[]` | Topic IDs set as recipients. |
| `users` | `string[]` | User IDs set as recipients. |
| `targets` | `string[]` | Target IDs set as recipients. |
| `scheduledAt` | `string` | The scheduled time for message. |
| `deliveredAt` | `string` | The time when the message was delivered. |
| `deliveryErrors` | `string[]` | Delivery errors if any. |
| `deliveredTotal` | `number` | Number of recipients the message was delivered to. |
| `data` | `object` | Data of the message. |
| `status` | `MessageStatus` | Status of delivery. |
