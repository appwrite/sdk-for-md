# getDeploymentDownload

Description: Get a function deployment content by its unique ID. The endpoint response return with a &#039;Content-Disposition: attachment&#039; header that tells the browser to start downloading the file to user downloads directory.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `deploymentId` | `string` | ✅ | Deployment ID. |
| `type` | `DeploymentDownloadType` | ❌ | Deployment file to download. Can be: &quot;source&quot;, &quot;output&quot;. (Default: `source`)<br>**Allowed:** `source`, `output` |

## Usage

```typescript
import { Client, Functions, DeploymentDownloadType } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result = functions.getDeploymentDownload({
  functionId: '<FUNCTION_ID>',
  deploymentId: '<DEPLOYMENT_ID>',
  type: DeploymentDownloadType.Source,
});
```
