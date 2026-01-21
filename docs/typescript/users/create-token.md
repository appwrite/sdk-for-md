# createToken

Description: Returns a token with a secret key for creating a session. Use the user ID and secret and submit a request to the [PUT /account/sessions/token](https://appwrite.io/docs/references/cloud/client-web/account#createSession) endpoint to complete the login process.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `length` | `number` | ❌ | Token length in characters. The default length is 6 characters (Default: `6`) |
| `expire` | `number` | ❌ | Token expiration period in seconds. The default expiration is 15 minutes. (Default: `900`) |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Token = await users.createToken({
  userId: '<USER_ID>',
  length: 4,
  expire: 60,
});
```

## Response Model

Returns a `Models.Token` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Token ID. |
| `createdAt` | `string` | Token creation date in ISO 8601 format. |
| `userId` | `string` | User ID. |
| `secret` | `string` | Token secret key. This will return an empty string unless the response is returned using an API key or as part of a webhook payload. |
| `expire` | `string` | Token expiration date in ISO 8601 format. |
| `phrase` | `string` | Security phrase of a token. Empty if security phrase was not requested when creating a token. It includes randomly generated phrase which is also sent in the external resource such as email. |
