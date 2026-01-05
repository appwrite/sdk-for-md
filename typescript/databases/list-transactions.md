# listTransactions

Description: List transactions across all databases.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). (Default: `[]`) |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.TransactionList = await databases.listTransactions({
  queries: [],
});
```

## Response Model

Returns a `Models.TransactionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of transactions that matched your query. |
| `transactions` | `object[]` | List of transactions. |
