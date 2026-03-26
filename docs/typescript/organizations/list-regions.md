# listRegions

Description: Get all available regions for an organization.

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
const result: Models.ConsoleRegionList = await organizations.listRegions({
  organizationId: '<ORGANIZATION_ID>',
});
```

## Response Model

Returns a `Models.ConsoleRegionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of regions that matched your query. |
| `regions` | `object[]` | List of regions. |
