# updateSessionAlerts

Description: Enable or disable session email alerts. When enabled, users will receive email notifications when new sessions are created.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `alerts` | `boolean` | ✅ | Set to true to enable session emails. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Project = await projects.updateSessionAlerts({
  projectId: '<PROJECT_ID>',
  alerts: false,
});
```

## Response Model

Returns a `Models.Project` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Project ID. |
| `createdAt` | `string` | Project creation date in ISO 8601 format. |
| `updatedAt` | `string` | Project update date in ISO 8601 format. |
| `name` | `string` | Project name. |
| `description` | `string` | Project description. |
| `teamId` | `string` | Project team ID. |
| `logo` | `string` | Project logo file ID. |
| `url` | `string` | Project website URL. |
| `legalName` | `string` | Company legal name. |
| `legalCountry` | `string` | Country code in [ISO 3166-1](http://en.wikipedia.org/wiki/ISO_3166-1) two-character format. |
| `legalState` | `string` | State name. |
| `legalCity` | `string` | City name. |
| `legalAddress` | `string` | Company Address. |
| `legalTaxId` | `string` | Company Tax ID. |
| `authDuration` | `number` | Session duration in seconds. |
| `authLimit` | `number` | Max users allowed. 0 is unlimited. |
| `authSessionsLimit` | `number` | Max sessions allowed per user. 100 maximum. |
| `authPasswordHistory` | `number` | Max allowed passwords in the history list per user. Max passwords limit allowed in history is 20. Use 0 for disabling password history. |
| `authPasswordDictionary` | `boolean` | Whether or not to check user&#039;s password against most commonly used passwords. |
| `authPersonalDataCheck` | `boolean` | Whether or not to check the user password for similarity with their personal data. |
| `authMockNumbers` | `object[]` | An array of mock numbers and their corresponding verification codes (OTPs). |
| `authSessionAlerts` | `boolean` | Whether or not to send session alert emails to users. |
| `authMembershipsUserName` | `boolean` | Whether or not to show user names in the teams membership response. |
| `authMembershipsUserEmail` | `boolean` | Whether or not to show user emails in the teams membership response. |
| `authMembershipsMfa` | `boolean` | Whether or not to show user MFA status in the teams membership response. |
| `authInvalidateSessions` | `boolean` | Whether or not all existing sessions should be invalidated on password change |
| `oAuthProviders` | `object[]` | List of Auth Providers. |
| `platforms` | `object[]` | List of Platforms. |
| `webhooks` | `object[]` | List of Webhooks. |
| `keys` | `object[]` | List of API Keys. |
| `devKeys` | `object[]` | List of dev keys. |
| `smtpEnabled` | `boolean` | Status for custom SMTP |
| `smtpSenderName` | `string` | SMTP sender name |
| `smtpSenderEmail` | `string` | SMTP sender email |
| `smtpReplyTo` | `string` | SMTP reply to email |
| `smtpHost` | `string` | SMTP server host name |
| `smtpPort` | `number` | SMTP server port |
| `smtpUsername` | `string` | SMTP server username |
| `smtpPassword` | `string` | SMTP server password |
| `smtpSecure` | `string` | SMTP server secure protocol |
| `pingCount` | `number` | Number of times the ping was received for this project. |
| `pingedAt` | `string` | Last ping datetime in ISO 8601 format. |
| `labels` | `string[]` | Labels for the project. |
| `status` | `string` | Project status |
| `authEmailPassword` | `boolean` | Email/Password auth method status |
| `authUsersAuthMagicURL` | `boolean` | Magic URL auth method status |
| `authEmailOtp` | `boolean` | Email (OTP) auth method status |
| `authAnonymous` | `boolean` | Anonymous auth method status |
| `authInvites` | `boolean` | Invites auth method status |
| `authJWT` | `boolean` | JWT auth method status |
| `authPhone` | `boolean` | Phone auth method status |
| `serviceStatusForAccount` | `boolean` | Account service status |
| `serviceStatusForAvatars` | `boolean` | Avatars service status |
| `serviceStatusForDatabases` | `boolean` | Databases (legacy) service status |
| `serviceStatusForTablesdb` | `boolean` | TablesDB service status |
| `serviceStatusForLocale` | `boolean` | Locale service status |
| `serviceStatusForHealth` | `boolean` | Health service status |
| `serviceStatusForStorage` | `boolean` | Storage service status |
| `serviceStatusForTeams` | `boolean` | Teams service status |
| `serviceStatusForUsers` | `boolean` | Users service status |
| `serviceStatusForSites` | `boolean` | Sites service status |
| `serviceStatusForFunctions` | `boolean` | Functions service status |
| `serviceStatusForGraphql` | `boolean` | GraphQL service status |
| `serviceStatusForMessaging` | `boolean` | Messaging service status |
| `region` | `string` | Project region |
| `billingLimits` | `object` | Billing limits reached |
| `blocks` | `object[]` | Project blocks information |
| `consoleAccessedAt` | `string` | Last time the project was accessed via console. Used with plan&#039;s projectInactivityDays to determine if project is paused. |
