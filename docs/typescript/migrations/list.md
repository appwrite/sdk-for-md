# list

Description: List all migrations in the current project. This endpoint returns a list of all migrations including their status, progress, and any errors that occurred during the migration process.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: status, stage, source, destination, resources, resourceId, resourceType, statusCounters, resourceData, errors (Default: `[]`) |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Migrations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.MigrationList = await migrations.list({
  queries: [],
  search: '<SEARCH>',
  total: false,
});
```

## Response Model

Returns a `Models.MigrationList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of migrations that matched your query. |
| `migrations` | `object[]` | List of migrations. |
