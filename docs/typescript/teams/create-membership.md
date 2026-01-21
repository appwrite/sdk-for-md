# createMembership

Description: Invite a new member to join your team. Provide an ID for existing users, or invite unregistered users using an email or phone number. If initiated from a Client SDK, Appwrite will send an email or sms with a link to join the team to the invited user, and an account will be created for them if one doesn&#039;t exist. If initiated from a Server SDK, the new member will be added automatically to the team.

You only need to provide one of a user ID, email, or phone number. Appwrite will prioritize accepting the user ID &gt; email &gt; phone number if you provide more than one of these parameters.

Use the `url` parameter to redirect the user from the invitation email to your app. After the user is redirected, use the [Update Team Membership Status](https://appwrite.io/docs/references/cloud/client-web/teams#updateMembershipStatus) endpoint to allow the user to accept the invitation to the team. 

Please note that to avoid a [Redirect Attack](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.md) Appwrite will accept the only redirect URLs under the domains you have added as a platform on the Appwrite Console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `teamId` | `string` | ✅ | Team ID. |
| `roles` | `string[]` | ✅ | Array of strings. Use this param to set the user roles in the team. A role can be any string. Learn more about [roles and permissions](https://appwrite.io/docs/permissions). Maximum of 100 roles are allowed, each 32 characters long. |
| `email` | `string` | ❌ | Email of the new team member. |
| `userId` | `string` | ❌ | ID of the user to be added to a team. |
| `phone` | `string` | ❌ | Phone number. Format this number with a leading &#039;+&#039; and a country code, e.g., +16175551212. |
| `url` | `string` | ❌ | URL to redirect the user back to your app from the invitation email. This parameter is not required when an API key is supplied. Only URLs from hostnames in your project platform list are allowed. This requirement helps to prevent an [open redirect](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html) attack against your project API. |
| `name` | `string` | ❌ | Name of the new team member. Max length: 128 chars. |

## Usage

```typescript
import { Client, Teams, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const teams = new Teams(client);
const result: Models.Membership = await teams.createMembership({
  teamId: '<TEAM_ID>',
  roles: [],
  email: 'email@example.com',
  userId: '<USER_ID>',
  phone: '+12065550100',
  url: 'https://example.com',
  name: '<NAME>',
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
