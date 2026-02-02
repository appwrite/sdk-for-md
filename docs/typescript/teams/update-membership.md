# updateMembership

Description: Modify the roles of a team member. Only team members with the owner role have access to this endpoint. Learn more about [roles and permissions](https://appwrite.io/docs/permissions).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `membershipId` | `string` | ✅ | Membership ID. |
| `roles` | `Roles` | ✅ | An array of strings. Use this param to set the user&#039;s roles in the team. A role can be any string. Learn more about [roles and permissions](https://appwrite.io/docs/permissions). Maximum of 100 roles are allowed, each 32 characters long.<br>**Allowed:** `admin`, `developer`, `owner` |

## Usage

```typescript
import { Client, Teams, Roles, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Membership = await teams.updateMembership({
  teamId: '<TEAM_ID>',
  membershipId: '<MEMBERSHIP_ID>',
  roles: Roles.Admin,
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
