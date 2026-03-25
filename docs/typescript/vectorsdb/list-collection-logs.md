# listCollectionLogs

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Only supported methods are limit and offset (Default: `[]`) |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.LogList = await vectorsDB.listCollectionLogs({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.LogList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of logs that matched your query. |
| `logs` | `object[]` | List of logs. |
