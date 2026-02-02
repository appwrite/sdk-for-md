# getPubSub

Description: Check the Appwrite pub-sub servers are up and connection is successful.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthStatusList = await health.getPubSub();
```

## Response Model

Returns a `Models.HealthStatusList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of statuses that matched your query. |
| `statuses` | `object[]` | List of statuses. |
