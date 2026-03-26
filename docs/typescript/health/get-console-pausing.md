# getConsolePausing

Description: Get console pausing health status. Monitors projects approaching the pause threshold to detect potential issues with console access tracking.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `threshold` | `number` | ❌ | Percentage threshold of projects approaching pause. When hit (equal or higher), endpoint returns server error. Default value is 10. (Default: `10`) |
| `inactivityDays` | `number` | ❌ | Number of days of inactivity before a project is paused. Should match the plan&#039;s projectInactivityDays setting. Default value is 7. (Default: `7`) |

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthStatus = await health.getConsolePausing({
  threshold: 0,
  inactivityDays: 0,
});
```

## Response Model

Returns a `Models.HealthStatus` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `name` | `string` | Name of the service. |
| `ping` | `number` | Duration in milliseconds how long the health check took. |
| `status` | `HealthCheckStatus` | Service status. Possible values are: `pass`, `fail` |
