# createPhoneVerification

Description: Use this endpoint to send a verification SMS to the currently logged in user. This endpoint is meant for use after updating a user&#039;s phone number using the [accountUpdatePhone](https://appwrite.io/docs/references/cloud/client-web/account#updatePhone) endpoint. Learn more about how to [complete the verification process](https://appwrite.io/docs/references/cloud/client-web/account#updatePhoneVerification). The verification code sent to the user&#039;s phone number is valid for 15 minutes.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Token = await account.createPhoneVerification();
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
