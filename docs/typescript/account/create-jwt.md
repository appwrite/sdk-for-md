# createJWT

Description: Use this endpoint to create a JSON Web Token. You can use the resulting JWT to authenticate on behalf of the current user when working with the Appwrite server-side API and SDKs. The JWT secret is valid for 15 minutes from its creation and will be invalid if the user will logout in that time frame.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `duration` | `number` | ❌ | Time in seconds before JWT expires. Default duration is 900 seconds, and maximum is 3600 seconds. (Default: `900`) |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Jwt = await account.createJWT({
  duration: 0,
});
```

## Response Model

Returns a `Models.Jwt` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `jwt` | `string` | JWT encoded string. |
