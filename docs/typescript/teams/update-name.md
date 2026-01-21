# updateName

Description: Update the team&#039;s name by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `name` | `string` | ✅ | New team name. Max length: 128 chars. |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Team = await teams.updateName({
  teamId: '<TEAM_ID>',
  name: '<NAME>',
});
```

## Response Model

Returns a `Models.Team` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Team ID. |
| `createdAt` | `string` | Team creation date in ISO 8601 format. |
| `updatedAt` | `string` | Team update date in ISO 8601 format. |
| `name` | `string` | Team name. |
| `total` | `number` | Total number of team members. |
| `prefs` | `object` | Team preferences as a key-value object |
