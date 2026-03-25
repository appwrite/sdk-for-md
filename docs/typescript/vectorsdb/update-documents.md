# updateDocuments

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `data` | `object` | ❌ | Document data as JSON object. Include only attribute and value pairs to be updated. (Default: `{}`) |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.DocumentList = await vectorsDB.updateDocuments({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  data: {},
  queries: [],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.DocumentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of documents that matched your query. |
| `documents` | `object[]` | List of documents. |
