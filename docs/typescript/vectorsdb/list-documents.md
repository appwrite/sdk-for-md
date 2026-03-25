# listDocuments

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID to read uncommitted changes within the transaction. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |
| `ttl` | `number` | ❌ | TTL (seconds) for cached responses when caching is enabled for select queries. Must be between 0 and 86400 (24 hours). |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.DocumentList = await vectorsDB.listDocuments({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  queries: [],
  transactionId: '<TRANSACTION_ID>',
  total: false,
  ttl: 0,
});
```

## Response Model

Returns a `Models.DocumentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of documents that matched your query. |
| `documents` | `object[]` | List of documents. |
