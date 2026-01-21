# createCSVExport

Description: Export documents to a CSV file from your Appwrite database. This endpoint allows you to export documents to a CSV file stored in a secure internal bucket. You&#039;ll receive an email with a download link when the export is complete.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `resourceId` | `string` | ✅ | Composite ID in the format {databaseId:collectionId}, identifying a collection within a database to export. |
| `filename` | `string` | ✅ | The name of the file to be created for the export, excluding the .csv extension. |
| `columns` | `string[]` | ❌ | List of attributes to export. If empty, all attributes will be exported. You can use the `*` wildcard to export all attributes from the collection. (Default: `[]`) |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK to filter documents to export. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `delimiter` | `string` | ❌ | The character that separates each column value. Default is comma. (Default: `,`) |
| `enclosure` | `string` | ❌ | The character that encloses each column value. Default is double quotes. (Default: `&quot;`) |
| `escape` | `string` | ❌ | The escape character for the enclosure character. Default is double quotes. (Default: `&quot;`) |
| `header` | `boolean` | ❌ | Whether to include the header row with column names. Default is true. (Default: `1`) |
| `notify` | `boolean` | ❌ | Set to true to receive an email when the export is complete. Default is true. (Default: `1`) |

## Usage

```typescript
import { Client, Migrations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.Migration = await migrations.createCSVExport({
  resourceId: '<ID1:ID2>',
  filename: '<FILENAME>',
  columns: [],
  queries: [],
  delimiter: '<DELIMITER>',
  enclosure: '<ENCLOSURE>',
  escape: '<ESCAPE>',
  header: false,
  notify: false,
});
```

## Response Model

Returns a `Models.Migration` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Migration ID. |
| `createdAt` | `string` | Migration creation date in ISO 8601 format. |
| `updatedAt` | `string` | Variable creation date in ISO 8601 format. |
| `status` | `string` | Migration status ( pending, processing, failed, completed )  |
| `stage` | `string` | Migration stage ( init, processing, source-check, destination-check, migrating, finished ) |
| `source` | `string` | A string containing the type of source of the migration. |
| `destination` | `string` | A string containing the type of destination of the migration. |
| `resources` | `string[]` | Resources to migrate. |
| `resourceId` | `string` | Id of the resource to migrate. |
| `statusCounters` | `object` | A group of counters that represent the total progress of the migration. |
| `resourceData` | `object` | An array of objects containing the report data of the resources that were migrated. |
| `errors` | `string[]` | All errors that occurred during the migration process. |
| `options` | `object` | Migration options used during the migration process. |
