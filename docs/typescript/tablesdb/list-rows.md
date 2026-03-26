# listRows

Description: Get a list of all the user&#039;s rows in a given table. You can use the query params to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the TablesDB service [server integration](https://appwrite.io/docs/products/databases/tables#create-table). |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID to read uncommitted changes within the transaction. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |
| `ttl` | `number` | ❌ | TTL (seconds) for cached responses when caching is enabled for select queries. Must be between 0 and 86400 (24 hours). |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.RowList = await tablesDB.listRows({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  queries: [],
  transactionId: '<TRANSACTION_ID>',
  total: false,
  ttl: 0,
});
```

## Response Model

Returns a `Models.RowList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of rows that matched your query. |
| `rows` | `object[]` | List of rows. |
