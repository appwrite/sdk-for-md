# getIndex

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). |
| `key` | `string` | ✅ | Index Key. |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.Index = await vectorsDB.getIndex({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
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
