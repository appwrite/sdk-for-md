# deleteVariable

Description: Delete a variable by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function unique ID. |
| `variableId` | `string` | ✅ | Variable unique ID. |

## Usage

```typescript
import { Client, Functions } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result = await functions.deleteVariable({
  functionId: '<FUNCTION_ID>',
  variableId: '<VARIABLE_ID>',
});
```
