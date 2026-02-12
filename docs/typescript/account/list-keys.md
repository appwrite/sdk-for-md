# listKeys

Description: Get a list of all API keys from the current account.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.KeyList = await account.listKeys({
  total: false,
});
```

## Response Model

Returns a `Models.KeyList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of keys that matched your query. |
| `keys` | `object[]` | List of keys. |
