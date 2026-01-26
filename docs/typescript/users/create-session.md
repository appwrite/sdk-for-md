# createSession

Description: Creates a session for a user. Returns an immediately usable session object.

If you want to generate a token for a custom authentication flow, use the [POST /users/{userId}/tokens](https://appwrite.io/docs/server/users#createToken) endpoint.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Session = await users.createSession({
  userId: '<USER_ID>',
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
