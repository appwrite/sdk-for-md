# getUsage

Description: Get usage metrics and statistics for all users in the project. You can view the total number of users and sessions. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Users, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.UsageUsers = await users.getUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageUsers` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `usersTotal` | `number` | Total aggregated number of statistics of users. |
| `sessionsTotal` | `number` | Total aggregated number of active sessions. |
| `users` | `object[]` | Aggregated number of users per period. |
| `sessions` | `object[]` | Aggregated number of active sessions  per period. |
