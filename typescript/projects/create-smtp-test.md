# createSMTPTest

Description: Send a test email to verify SMTP configuration.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `emails` | `string[]` | ✅ | Array of emails to send test email to. Maximum of 10 emails are allowed. |
| `senderName` | `string` | ✅ | Name of the email sender |
| `senderEmail` | `string` | ✅ | Email of the sender |
| `host` | `string` | ✅ | SMTP server host name |
| `replyTo` | `string` | ❌ | Reply to email |
| `port` | `number` | ❌ | SMTP server port (Default: `587`) |
| `username` | `string` | ❌ | SMTP server username |
| `password` | `string` | ❌ | SMTP server password |
| `secure` | `SMTPSecure` | ❌ | Does SMTP server use secure connection<br>**Allowed:** `tls`, `ssl` |

## Usage

```typescript
import { Client, Projects, SMTPSecure } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.createSMTPTest({
  projectId: '<PROJECT_ID>',
  emails: [],
  senderName: '<SENDER_NAME>',
  senderEmail: 'email@example.com',
  host: '',
  replyTo: 'email@example.com',
  port: 0,
  username: '<USERNAME>',
  password: '<PASSWORD>',
  secure: SMTPSecure.Tls,
});
```
