# listInvoices

Description: List all invoices tied to an account.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: teamId, aggregationId, type, amount, currency, from, to, dueAt, attempts, status, grossAmount (Default: `[]`) |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.InvoiceList = await account.listInvoices({
  queries: [],
});
```

## Response Model

Returns a `Models.InvoiceList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of invoices that matched your query. |
| `invoices` | `object[]` | List of invoices. |
