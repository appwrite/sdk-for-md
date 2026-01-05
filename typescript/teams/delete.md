# delete

Description: Delete a team using its ID. Only team members with the owner role can delete the team.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |

## Usage

```typescript
import { Client, Teams } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result = await teams.delete({
  teamId: '<TEAM_ID>',
});
```
