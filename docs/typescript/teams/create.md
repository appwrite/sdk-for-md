# create

Description: Create a new team. The user who creates the team will automatically be assigned as the owner of the team. Only the users with the owner role can invite new members, add new owners and delete or update the team.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Team name. Max length: 128 chars. |
| `roles` | `string[]` | ❌ | Array of strings. Use this param to set the roles in the team for the user who created it. The default role is **owner**. A role can be any string. Learn more about [roles and permissions](https://appwrite.io/docs/permissions). Maximum of 100 roles are allowed, each 32 characters long. (Default: `[&quot;owner&quot;]`) |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Team = await teams.create({
  teamId: '<TEAM_ID>',
  name: '<NAME>',
  roles: [],
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
