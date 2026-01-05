# deleteVariable

Description: Delete a variable by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site unique ID. |
| `variableId` | `string` | ✅ | Variable unique ID. |

## Usage

```typescript
import { Client, Sites } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result = await sites.deleteVariable({
  siteId: '<SITE_ID>',
  variableId: '<VARIABLE_ID>',
});
```
