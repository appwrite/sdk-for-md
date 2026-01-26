# deleteMembership

Description: This endpoint allows a user to leave a team or for a team owner to delete the membership of any other team member. You can also use this endpoint to delete a user membership even if it is not accepted.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `membershipId` | `string` | ✅ | Membership ID. |

## Usage

```typescript
import { Client, Teams } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result = await teams.deleteMembership({
  teamId: '<TEAM_ID>',
  membershipId: '<MEMBERSHIP_ID>',
});
```
