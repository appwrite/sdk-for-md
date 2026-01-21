# listDocuments

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.listRows` instead

Description: Get a list of all the user&#039;s documents in a given collection. You can use the query params to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID to read uncommitted changes within the transaction. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.DocumentList = await databases.listDocuments({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  queries: [],
  transactionId: '<TRANSACTION_ID>',
  total: false,
});
```

## Response Model

Returns a `Models.DocumentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of documents that matched your query. |
| `documents` | `object[]` | List of documents. |
