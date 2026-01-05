# deleteLog

Description: Delete a site log by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `logId` | `string` | ✅ | Log ID. |

## Usage

```typescript
import { Client, Sites } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result = await sites.deleteLog({
  siteId: '<SITE_ID>',
  logId: '<LOG_ID>',
});
```
