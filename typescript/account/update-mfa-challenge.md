# updateMFAChallenge

Description: Complete the MFA challenge by providing the one-time password. Finish the process of MFA verification by providing the one-time password. To begin the flow, use [createMfaChallenge](/docs/references/cloud/client-web/account#createMfaChallenge) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `challengeId` | `string` | ✅ | ID of the challenge. |
| `otp` | `string` | ✅ | Valid verification token. |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Session = await account.updateMFAChallenge({
  challengeId: '<CHALLENGE_ID>',
  otp: '<OTP>',
});
```

## Response Model

Returns a `Models.Session` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Session ID. |
| `createdAt` | `string` | Session creation date in ISO 8601 format. |
| `updatedAt` | `string` | Session update date in ISO 8601 format. |
| `userId` | `string` | User ID. |
| `expire` | `string` | Session expiration date in ISO 8601 format. |
| `provider` | `string` | Session Provider. |
| `providerUid` | `string` | Session Provider User ID. |
| `providerAccessToken` | `string` | Session Provider Access Token. |
| `providerAccessTokenExpiry` | `string` | The date of when the access token expires in ISO 8601 format. |
| `providerRefreshToken` | `string` | Session Provider Refresh Token. |
| `ip` | `string` | IP in use when the session was created. |
| `osCode` | `string` | Operating system code name. View list of [available options](https://github.com/appwrite/appwrite/blob/master/docs/lists/os.json). |
| `osName` | `string` | Operating system name. |
| `osVersion` | `string` | Operating system version. |
| `clientType` | `string` | Client type. |
| `clientCode` | `string` | Client code name. View list of [available options](https://github.com/appwrite/appwrite/blob/master/docs/lists/clients.json). |
| `clientName` | `string` | Client name. |
| `clientVersion` | `string` | Client version. |
| `clientEngine` | `string` | Client engine name. |
| `clientEngineVersion` | `string` | Client engine name. |
| `deviceName` | `string` | Device name. |
| `deviceBrand` | `string` | Device brand name. |
| `deviceModel` | `string` | Device model name. |
| `countryCode` | `string` | Country two-character ISO 3166-1 alpha code. |
| `countryName` | `string` | Country name. |
| `current` | `boolean` | Returns true if this the current user session. |
| `factors` | `string[]` | Returns a list of active session factors. |
| `secret` | `string` | Secret used to authenticate the user. Only included if the request was made with an API key |
| `mfaUpdatedAt` | `string` | Most recent date in ISO 8601 format when the session successfully passed MFA challenge. |
