# deleteExecution

Description: Delete a function execution by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `executionId` | `string` | ✅ | Execution ID. |

## Usage

```typescript
import { Client, Functions } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result = await functions.deleteExecution({
  functionId: '<FUNCTION_ID>',
  executionId: '<EXECUTION_ID>',
});
```
