# getPrefs

Description: Get the user preferences by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Preferences = await users.getPrefs({
  userId: '<USER_ID>',
});
```

## Response Model

Returns a `Models.Preferences` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
