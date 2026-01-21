# getMembership

Description: Get a team member by the membership unique id. All team members have read access for this resource. Hide sensitive attributes from the response by toggling membership privacy in the Console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `membershipId` | `string` | ✅ | Membership ID. |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Membership = await teams.getMembership({
  teamId: '<TEAM_ID>',
  membershipId: '<MEMBERSHIP_ID>',
});
```

## Response Model

Returns a `Models.Membership` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Membership ID. |
| `createdAt` | `string` | Membership creation date in ISO 8601 format. |
| `updatedAt` | `string` | Membership update date in ISO 8601 format. |
| `userId` | `string` | User ID. |
| `userName` | `string` | User name. Hide this attribute by toggling membership privacy in the Console. |
| `userEmail` | `string` | User email address. Hide this attribute by toggling membership privacy in the Console. |
| `teamId` | `string` | Team ID. |
| `teamName` | `string` | Team name. |
| `invited` | `string` | Date, the user has been invited to join the team in ISO 8601 format. |
| `joined` | `string` | Date, the user has accepted the invitation to join the team in ISO 8601 format. |
| `confirm` | `boolean` | User confirmation status, true if the user has joined the team or false otherwise. |
| `mfa` | `boolean` | Multi factor authentication status, true if the user has MFA enabled or false otherwise. Hide this attribute by toggling membership privacy in the Console. |
| `roles` | `string[]` | User list of roles |
