# listPaymentMethods

Description: List payment methods for this account.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: userId, expired, failed (Default: `[]`) |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.PaymentMethodList = await account.listPaymentMethods({
  queries: [],
});
```

## Response Model

Returns a `Models.PaymentMethodList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of paymentMethods that matched your query. |
| `paymentMethods` | `object[]` | List of paymentMethods. |
