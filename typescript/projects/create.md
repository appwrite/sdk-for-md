# create

Description: Create a new project. You can create a maximum of 100 projects per account.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, and hyphen. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Project name. Max length: 128 chars. |
| `teamId` | `string` | ✅ | Team unique ID. |
| `region` | `Region` | ❌ | Project Region. (Default: `default`)<br>**Allowed:** `default` |
| `description` | `string` | ❌ | Project description. Max length: 256 chars. |
| `logo` | `string` | ❌ | Project logo. |
| `url` | `string` | ❌ | Project URL. |
| `legalName` | `string` | ❌ | Project legal Name. Max length: 256 chars. |
| `legalCountry` | `string` | ❌ | Project legal Country. Max length: 256 chars. |
| `legalState` | `string` | ❌ | Project legal State. Max length: 256 chars. |
| `legalCity` | `string` | ❌ | Project legal City. Max length: 256 chars. |
| `legalAddress` | `string` | ❌ | Project legal Address. Max length: 256 chars. |
| `legalTaxId` | `string` | ❌ | Project legal Tax ID. Max length: 256 chars. |

## Usage

```typescript
import { Client, Projects, Region, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Project = await projects.create({
  projectId: '',
  name: '<NAME>',
  teamId: '<TEAM_ID>',
  region: Region.Default,
  description: '<DESCRIPTION>',
  logo: '<LOGO>',
  url: 'https://example.com',
  legalName: '<LEGAL_NAME>',
  legalCountry: '<LEGAL_COUNTRY>',
  legalState: '<LEGAL_STATE>',
  legalCity: '<LEGAL_CITY>',
  legalAddress: '<LEGAL_ADDRESS>',
  legalTaxId: '<LEGAL_TAX_ID>',
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
