# deleteDeployment

Description: Delete a site deployment by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `deploymentId` | `string` | ✅ | Deployment ID. |

## Usage

```typescript
import { Client, Sites } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result = await sites.deleteDeployment({
  siteId: '<SITE_ID>',
  deploymentId: '<DEPLOYMENT_ID>',
});
```
