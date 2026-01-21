# createPhoneToken

Description: Sends the user an SMS with a secret key for creating a session. If the provided user ID has not be registered, a new user will be created. Use the returned user ID and secret and submit a request to the [POST /v1/account/sessions/token](https://appwrite.io/docs/references/cloud/client-web/account#createSession) endpoint to complete the login process. The secret sent to the user&#039;s phone is valid for 15 minutes.

A user is limited to 10 active sessions at a time by default. [Learn more about session limits](https://appwrite.io/docs/authentication-security#limits).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. If the phone number has never been used, a new account is created using the provided userId. Otherwise, if the phone number is already attached to an account, the user ID is ignored. |
| `phone` | `string` | ✅ | Phone number. Format this number with a leading &#039;+&#039; and a country code, e.g., +16175551212. |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Token = await account.createPhoneToken({
  userId: '<USER_ID>',
  phone: '+12065550100',
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
