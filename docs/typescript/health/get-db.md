# getDB

Description: Check the Appwrite database servers are up and connection is successful.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthStatus = await health.getDB();
```

## Response Model

Returns a `Models.HealthStatus` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `name` | `string` | Name of the service. |
| `ping` | `number` | Duration in milliseconds how long the health check took. |
| `status` | `HealthCheckStatus` | Service status. Possible values are: `pass`, `fail` |
