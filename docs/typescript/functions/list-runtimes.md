# listRuntimes

Description: Get a list of all runtimes that are currently active on your instance.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.RuntimeList = await functions.listRuntimes();
```

## Response Model

Returns a `Models.RuntimeList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of runtimes that matched your query. |
| `runtimes` | `object[]` | List of runtimes. |
