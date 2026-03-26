# listRegions

Description: Get all available regions for the console.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.ConsoleRegionList = await console.listRegions();
```

## Response Model

Returns a `Models.ConsoleRegionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of regions that matched your query. |
| `regions` | `object[]` | List of regions. |
