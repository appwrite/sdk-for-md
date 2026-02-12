# getAvailableCredits

Description: Get total available valid credits for an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.CreditAvailable = await organizations.getAvailableCredits({
  organizationId: '<ORGANIZATION_ID>',
});
```

## Response Model

Returns a `Models.CreditAvailable` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `available` | `number` | Total available credits for the organization. |
