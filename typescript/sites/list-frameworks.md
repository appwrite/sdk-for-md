# listFrameworks

Description: Get a list of all frameworks that are currently available on the server instance.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.FrameworkList = await sites.listFrameworks();
```

## Response Model

Returns a `Models.FrameworkList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of frameworks that matched your query. |
| `frameworks` | `object[]` | List of frameworks. |
