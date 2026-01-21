# getTableUsage

Description: Get usage metrics and statistics for a table. Returning the total number of rows. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, TablesDB, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.UsageTable = await tablesDB.getTableUsage({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageTable` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `rowsTotal` | `number` | Total aggregated number of of rows. |
| `rows` | `object[]` | Aggregated  number of rows per period. |
