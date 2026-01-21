# createPush

Description: Create a new push notification.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `messageId` | `string` | ✅ | Message ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `title` | `string` | ❌ | Title for push notification. |
| `body` | `string` | ❌ | Body for push notification. |
| `topics` | `string[]` | ❌ | List of Topic IDs. (Default: `[]`) |
| `users` | `string[]` | ❌ | List of User IDs. (Default: `[]`) |
| `targets` | `string[]` | ❌ | List of Targets IDs. (Default: `[]`) |
| `data` | `object` | ❌ | Additional key-value pair data for push notification. (Default: `{}`) |
| `action` | `string` | ❌ | Action for push notification. |
| `image` | `string` | ❌ | Image for push notification. Must be a compound bucket ID to file ID of a jpeg, png, or bmp image in Appwrite Storage. It should be formatted as &lt;BUCKET_ID&gt;:&lt;FILE_ID&gt;. |
| `icon` | `string` | ❌ | Icon for push notification. Available only for Android and Web Platform. |
| `sound` | `string` | ❌ | Sound for push notification. Available only for Android and iOS Platform. |
| `color` | `string` | ❌ | Color for push notification. Available only for Android Platform. |
| `tag` | `string` | ❌ | Tag for push notification. Available only for Android Platform. |
| `badge` | `number` | ❌ | Badge for push notification. Available only for iOS Platform. (Default: `-1`) |
| `draft` | `boolean` | ❌ | Is message a draft |
| `scheduledAt` | `string` | ❌ | Scheduled delivery time for message in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. DateTime value must be in future. |
| `contentAvailable` | `boolean` | ❌ | If set to true, the notification will be delivered in the background. Available only for iOS Platform. |
| `critical` | `boolean` | ❌ | If set to true, the notification will be marked as critical. This requires the app to have the critical notification entitlement. Available only for iOS Platform. |
| `priority` | `MessagePriority` | ❌ | Set the notification priority. &quot;normal&quot; will consider device state and may not deliver notifications immediately. &quot;high&quot; will always attempt to immediately deliver the notification. (Default: `high`)<br>**Allowed:** `normal`, `high` |

## Usage

```typescript
import { Client, Messaging, MessagePriority, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Message = await messaging.createPush({
  messageId: '<MESSAGE_ID>',
  title: '<TITLE>',
  body: '<BODY>',
  topics: [],
  users: [],
  targets: [],
  data: {},
  action: '<ACTION>',
  image: '<ID1:ID2>',
  icon: '<ICON>',
  sound: '<SOUND>',
  color: '<COLOR>',
  tag: '<TAG>',
  badge: 0,
  draft: false,
  scheduledAt: '',
  contentAvailable: false,
  critical: false,
  priority: MessagePriority.Normal,
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
