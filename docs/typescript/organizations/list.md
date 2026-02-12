# list

Description: Get a list of all the teams in which the current user is a member. You can use the parameters to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: name, total, billingPlan, paymentMethodId, backupPaymentMethodId, platform (Default: `[]`) |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.OrganizationList = await organizations.list({
  queries: [],
  search: '<SEARCH>',
});
```

## Response Model

Returns a `Models.OrganizationList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of teams that matched your query. |
| `teams` | `object[]` | List of teams. |
