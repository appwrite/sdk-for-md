# getPrefs

Description: Get the team&#039;s shared preferences by its unique ID. If a preference doesn&#039;t need to be shared by all team members, prefer storing them in [user preferences](https://appwrite.io/docs/references/cloud/client-web/account#getPrefs).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Preferences = await teams.getPrefs({
  teamId: '<TEAM_ID>',
});
```

## Response Model

Returns a `Models.Preferences` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
