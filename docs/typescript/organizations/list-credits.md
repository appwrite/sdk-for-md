# listCredits

Description: List all credits for an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: teamId, couponId, credits, expiration, status (Default: `[]`) |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.CreditList = await organizations.listCredits({
  organizationId: '<ORGANIZATION_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.CreditList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `credits` | `object[]` | Credits |
| `total` | `number` | Total number of credits |
| `available` | `number` | Total available credit balance in USD |
