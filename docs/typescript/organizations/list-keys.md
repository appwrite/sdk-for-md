# listKeys

Description: Get a list of all API keys from the current organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization Unique ID |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.KeyList = await organizations.listKeys({
  organizationId: '<ORGANIZATION_ID>',
  total: false,
});
```

## Response Model

Returns a `Models.KeyList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of keys that matched your query. |
| `keys` | `object[]` | List of keys. |
