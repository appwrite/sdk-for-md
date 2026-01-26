# listTemplates

Description: List available function templates. You can use template details in [createFunction](/docs/references/cloud/server-nodejs/functions#create) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `runtimes` | `string[]` | ❌ | List of runtimes allowed for filtering function templates. Maximum of 100 runtimes are allowed. (Default: `[]`) |
| `useCases` | `string[]` | ❌ | List of use cases allowed for filtering function templates. Maximum of 100 use cases are allowed. (Default: `[]`) |
| `limit` | `number` | ❌ | Limit the number of templates returned in the response. Default limit is 25, and maximum limit is 5000. (Default: `25`) |
| `offset` | `number` | ❌ | Offset the list of returned templates. Maximum offset is 5000. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.TemplateFunctionList = await functions.listTemplates({
  runtimes: [],
  useCases: [],
  limit: 1,
  offset: 0,
  total: false,
});
```

## Response Model

Returns a `Models.TemplateFunctionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of templates that matched your query. |
| `templates` | `object[]` | List of templates. |
