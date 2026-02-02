# getAppwriteReport

Description: Generate a report of the data in an Appwrite project before migrating. This endpoint analyzes the source project and returns information about the resources that can be migrated.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `resources` | `Resources` | ✅ | List of resources to migrate<br>**Allowed:** `user`, `team`, `membership`, `database`, `table`, `column`, `index`, `row`, `document`, `attribute`, `collection`, `bucket`, `file`, `function`, `deployment`, `environment-variable` |
| `endpoint` | `string` | ✅ | Source&#039;s Appwrite Endpoint |
| `projectID` | `string` | ✅ | Source&#039;s Project ID |
| `key` | `string` | ✅ | Source&#039;s API Key |

## Usage

```typescript
import { Client, Migrations, Resources, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.MigrationReport = await migrations.getAppwriteReport({
  resources: Resources.User,
  endpoint: 'https://example.com',
  projectID: '<PROJECT_ID>',
  key: '<KEY>',
});
```

## Response Model

Returns a `Models.MigrationReport` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `user` | `number` | Number of users to be migrated. |
| `team` | `number` | Number of teams to be migrated. |
| `database` | `number` | Number of databases to be migrated. |
| `row` | `number` | Number of rows to be migrated. |
| `file` | `number` | Number of files to be migrated. |
| `bucket` | `number` | Number of buckets to be migrated. |
| `function` | `number` | Number of functions to be migrated. |
| `size` | `number` | Size of files to be migrated in mb. |
| `version` | `string` | Version of the Appwrite instance to be migrated. |
