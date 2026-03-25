# createIndex

Description: Creates an index on the attributes listed. Your index should include all the attributes you will query in a single request.
Attributes can be `key`, `fulltext`, and `unique`.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). |
| `key` | `string` | ✅ | Index Key. |
| `type` | `DocumentsDBIndexType` | ✅ | Index type.<br>**Allowed:** `key`, `fulltext`, `unique`, `spatial` |
| `attributes` | `string[]` | ✅ | Array of attributes to index. Maximum of 100 attributes are allowed, each 32 characters long. |
| `orders` | `OrderBy` | ❌ | Array of index orders. Maximum of 100 orders are allowed. (Default: `[]`)<br>**Allowed:** `asc`, `desc` |
| `lengths` | `number[]` | ❌ | Length of index. Maximum of 100 (Default: `[]`) |

## Usage

```typescript
import { Client, DocumentsDB, DocumentsDBIndexType, OrderBy, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.Index = await documentsDB.createIndex({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  type: DocumentsDBIndexType.Key,
  attributes: [],
  orders: OrderBy.Asc,
  lengths: [],
});
```

## Response Model

Returns a `Models.Index` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Index ID. |
| `createdAt` | `string` | Index creation date in ISO 8601 format. |
| `updatedAt` | `string` | Index update date in ISO 8601 format. |
| `key` | `string` | Index key. |
| `type` | `string` | Index type. |
| `status` | `IndexStatus` | Index status. Possible values: `available`, `processing`, `deleting`, `stuck`, or `failed` |
| `error` | `string` | Error message. Displays error generated on failure of creating or deleting an index. |
| `attributes` | `string[]` | Index attributes. |
| `lengths` | `number[]` | Index attributes length. |
| `orders` | `string[]` | Index orders. |
