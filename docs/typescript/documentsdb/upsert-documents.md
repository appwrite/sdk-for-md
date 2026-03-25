# upsertDocuments

Description: Create or update Documents. Before using this route, you should create a new collection resource using either a [server integration](https://appwrite.io/docs/server/databases#documentsDBCreateCollection) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `documents` | `object[]` | ✅ | Array of document data as JSON objects. May contain partial documents. |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, DocumentsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.DocumentList = await documentsDB.upsertDocuments({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  documents: [],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.DocumentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of documents that matched your query. |
| `documents` | `object[]` | List of documents. |
