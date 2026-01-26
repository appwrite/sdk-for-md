# listVariables

Description: Get a list of all variables of a specific function.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function unique ID. |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.VariableList = await functions.listVariables({
  functionId: '<FUNCTION_ID>',
});
```

## Response Model

Returns a `Models.VariableList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of variables that matched your query. |
| `variables` | `object[]` | List of variables. |
