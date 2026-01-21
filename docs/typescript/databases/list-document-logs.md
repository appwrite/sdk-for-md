# listDocumentLogs

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.listRowLogs` instead

Description: Get the document activity logs list by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `documentId` | `string` | ✅ | Document ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Only supported methods are limit and offset (Default: `[]`) |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.LogList = await databases.listDocumentLogs({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  documentId: '<DOCUMENT_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.LogList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of logs that matched your query. |
| `logs` | `object[]` | List of logs. |
