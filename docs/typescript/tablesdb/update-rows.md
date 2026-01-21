# updateRows

Description: Update all rows that match your queries, if no queries are submitted then all rows are updated. You can pass only specific fields to be updated.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `data` | `object` | ❌ | Row data as JSON object. Include only column and value pairs to be updated. (Default: `{}`) |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.RowList = await tablesDB.updateRows({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  data: {
    "username": "walter.obrien",
    "email": "walter.obrien@example.com",
    "fullName": "Walter O'Brien",
    "age": 33,
    "isAdmin": false
},
  queries: [],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.RowList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of rows that matched your query. |
| `rows` | `object[]` | List of rows. |
