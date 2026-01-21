# updatePrefs

Description: Update the team&#039;s preferences by its unique ID. The object you pass is stored as is and replaces any previous value. The maximum allowed prefs size is 64kB and throws an error if exceeded.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `prefs` | `object` | ✅ | Prefs key-value JSON object. (Default: `{}`) |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Preferences = await teams.updatePrefs({
  teamId: '<TEAM_ID>',
  prefs: {},
});
```

## Response Model

Returns a `Models.Preferences` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
