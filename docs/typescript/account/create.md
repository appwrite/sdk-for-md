# create

Description: Use this endpoint to allow a new user to register a new account in your project. After the user registration completes successfully, you can use the [/account/verfication](https://appwrite.io/docs/references/cloud/client-web/account#createVerification) route to start verifying the user email address. To allow the new user to login to their new account, you need to create a new [account session](https://appwrite.io/docs/references/cloud/client-web/account#createEmailSession).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `email` | `string` | ✅ | User email. |
| `password` | `string` | ✅ | New user password. Must be between 8 and 256 chars. |
| `name` | `string` | ❌ | User name. Max length: 128 chars. |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.User = await account.create({
  userId: '<USER_ID>',
  email: 'email@example.com',
  password: '',
  name: '<NAME>',
});
```

## Response Model

Returns a `Models.User` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | User ID. |
| `createdAt` | `string` | User creation date in ISO 8601 format. |
| `updatedAt` | `string` | User update date in ISO 8601 format. |
| `name` | `string` | User name. |
| `password` | `string` | Hashed user password. |
| `hash` | `string` | Password hashing algorithm. |
| `hashOptions` | `object` | Password hashing algorithm configuration. |
| `registration` | `string` | User registration date in ISO 8601 format. |
| `status` | `boolean` | User status. Pass `true` for enabled and `false` for disabled. |
| `labels` | `string[]` | Labels for the user. |
| `passwordUpdate` | `string` | Password update time in ISO 8601 format. |
| `email` | `string` | User email address. |
| `phone` | `string` | User phone number in E.164 format. |
| `emailVerification` | `boolean` | Email verification status. |
| `phoneVerification` | `boolean` | Phone verification status. |
| `mfa` | `boolean` | Multi factor authentication status. |
| `prefs` | `object` | User preferences as a key-value object |
| `targets` | `object[]` | A user-owned message receiver. A single user may have multiple e.g. emails, phones, and a browser. Each target is registered with a single provider. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
