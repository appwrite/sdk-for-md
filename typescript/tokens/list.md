# list

Description: List all the tokens created for a specific file or bucket. You can use the query params to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File unique ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: expire (Default: `[]`) |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Tokens, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tokens = new Tokens(client);
const result: Models.ResourceTokenList = await tokens.list({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  queries: [],
  total: false,
});
```

## Response Model

Returns a `Models.ResourceTokenList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of tokens that matched your query. |
| `tokens` | `object[]` | List of tokens. |
