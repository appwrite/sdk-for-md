# updateSMTPProvider

Description: Update a SMTP provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `host` | `string` | ❌ | SMTP hosts. Either a single hostname or multiple semicolon-delimited hostnames. You can also specify a different port for each host such as `smtp1.example.com:25;smtp2.example.com`. You can also specify encryption type, for example: `tls://smtp1.example.com:587;ssl://smtp2.example.com:465&quot;`. Hosts will be tried in order. |
| `port` | `number` | ❌ | SMTP port. |
| `username` | `string` | ❌ | Authentication username. |
| `password` | `string` | ❌ | Authentication password. |
| `encryption` | `SmtpEncryption` | ❌ | Encryption type. Can be &#039;ssl&#039; or &#039;tls&#039;<br>**Allowed:** `none`, `ssl`, `tls` |
| `autoTLS` | `boolean` | ❌ | Enable SMTP AutoTLS feature. |
| `mailer` | `string` | ❌ | The value to use for the X-Mailer header. |
| `fromName` | `string` | ❌ | Sender Name. |
| `fromEmail` | `string` | ❌ | Sender email address. |
| `replyToName` | `string` | ❌ | Name set in the Reply To field for the mail. Default value is Sender Name. |
| `replyToEmail` | `string` | ❌ | Email set in the Reply To field for the mail. Default value is Sender Email. |
| `enabled` | `boolean` | ❌ | Set as enabled. |

## Usage

```typescript
import { Client, Messaging, SmtpEncryption, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateSMTPProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  host: '<HOST>',
  port: 1,
  username: '<USERNAME>',
  password: '<PASSWORD>',
  encryption: SmtpEncryption.None,
  autoTLS: false,
  mailer: '<MAILER>',
  fromName: '<FROM_NAME>',
  fromEmail: 'email@example.com',
  replyToName: '<REPLY_TO_NAME>',
  replyToEmail: '<REPLY_TO_EMAIL>',
  enabled: false,
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
