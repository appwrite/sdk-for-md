# estimationDeleteOrganization

Description: Get estimation for deleting an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Team ID. |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.EstimationDeleteOrganization = await organizations.estimationDeleteOrganization({
  organizationId: '<ORGANIZATION_ID>',
});
```

## Response Model

Returns a `Models.EstimationDeleteOrganization` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `unpaidInvoices` | `object[]` | List of unpaid invoices |
