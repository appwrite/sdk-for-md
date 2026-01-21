# deleteDeployment

Description: Delete a code deployment by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `deploymentId` | `string` | ✅ | Deployment ID. |

## Usage

```typescript
import { Client, Functions } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result = await functions.deleteDeployment({
  functionId: '<FUNCTION_ID>',
  deploymentId: '<DEPLOYMENT_ID>',
});
```
