# updateMailgunProvider

Description: Update a Mailgun provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `apiKey` | `string` | ❌ | Mailgun API Key. |
| `domain` | `string` | ❌ | Mailgun Domain. |
| `isEuRegion` | `boolean` | ❌ | Set as EU region. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `fromName` | `string` | ❌ | Sender Name. |
| `fromEmail` | `string` | ❌ | Sender email address. |
| `replyToName` | `string` | ❌ | Name set in the reply to field for the mail. Default value is sender name. |
| `replyToEmail` | `string` | ❌ | Email set in the reply to field for the mail. Default value is sender email. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateMailgunProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  apiKey: '<API_KEY>',
  domain: '<DOMAIN>',
  isEuRegion: false,
  enabled: false,
  fromName: '<FROM_NAME>',
  fromEmail: 'email@example.com',
  replyToName: '<REPLY_TO_NAME>',
  replyToEmail: '<REPLY_TO_EMAIL>',
});
```

## Response Model

Returns a `Models.Provider` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Provider ID. |
| `createdAt` | `string` | Provider creation time in ISO 8601 format. |
| `updatedAt` | `string` | Provider update date in ISO 8601 format. |
| `name` | `string` | The name for the provider instance. |
| `provider` | `string` | The name of the provider service. |
| `enabled` | `boolean` | Is provider enabled? |
| `type` | `string` | Type of provider. |
| `credentials` | `object` | Provider credentials. |
| `options` | `object` | Provider options. |
