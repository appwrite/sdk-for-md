# getCampaign

Description: Receive the details of a campaign using its ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `campaignId` | `string` | ✅ | ID of the campaign |

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.Campaign = await console.getCampaign({
  campaignId: '<CAMPAIGN_ID>',
});
```

## Response Model

Returns a `Models.Campaign` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Campaign ID |
| `template` | `string` | Campaign template |
| `title` | `string` | Campaign title |
| `description` | `string` | Campaign description |
| `plan` | `string` | Billing plan campaign is associated with |
| `cta` | `string` | Campaign CTA |
| `claimed` | `string` | Campaign info when claimed |
| `unclaimed` | `string` | Campaign infor when unclaimed |
| `image` | `object` | Campaign images |
| `reviews` | `object[]` | Campaign reviews |
| `onlyNewOrgs` | `boolean` | Campaign valid only for new orgs. |
| `footer` | `boolean` | Is footer |
