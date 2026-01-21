# updatePrefs

Description: Update the user preferences by its unique ID. The object you pass is stored as is, and replaces any previous value. The maximum allowed prefs size is 64kB and throws error if exceeded.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `prefs` | `object` | ✅ | Prefs key-value JSON object. (Default: `{}`) |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Preferences = await users.updatePrefs({
  userId: '<USER_ID>',
  prefs: {},
});
```

## Response Model

Returns a `Models.Preferences` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
