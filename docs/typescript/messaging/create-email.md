# createEmail

Description: Create a new email message.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `messageId` | `string` | ✅ | Message ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `subject` | `string` | ✅ | Email Subject. |
| `content` | `string` | ✅ | Email Content. |
| `topics` | `string[]` | ❌ | List of Topic IDs. (Default: `[]`) |
| `users` | `string[]` | ❌ | List of User IDs. (Default: `[]`) |
| `targets` | `string[]` | ❌ | List of Targets IDs. (Default: `[]`) |
| `cc` | `string[]` | ❌ | Array of target IDs to be added as CC. (Default: `[]`) |
| `bcc` | `string[]` | ❌ | Array of target IDs to be added as BCC. (Default: `[]`) |
| `attachments` | `string[]` | ❌ | Array of compound ID strings of bucket IDs and file IDs to be attached to the email. They should be formatted as &lt;BUCKET_ID&gt;:&lt;FILE_ID&gt;. (Default: `[]`) |
| `draft` | `boolean` | ❌ | Is message a draft |
| `html` | `boolean` | ❌ | Is content of type HTML |
| `scheduledAt` | `string` | ❌ | Scheduled delivery time for message in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. DateTime value must be in future. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Message = await messaging.createEmail({
  messageId: '<MESSAGE_ID>',
  subject: '<SUBJECT>',
  content: '<CONTENT>',
  topics: [],
  users: [],
  targets: [],
  cc: [],
  bcc: [],
  attachments: [],
  draft: false,
  html: false,
  scheduledAt: '',
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
