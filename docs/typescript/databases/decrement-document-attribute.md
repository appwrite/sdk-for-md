# decrementDocumentAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.decrementRowColumn` instead

Description: Decrement a specific attribute of a document by a given value.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `documentId` | `string` | ✅ | Document ID. |
| `attribute` | `string` | ✅ | Attribute key. |
| `value` | `number` | ❌ | Value to increment the attribute by. The value must be a number. (Default: `1`) |
| `min` | `number` | ❌ | Minimum value for the attribute. If the current value is lesser than this value, an exception will be thrown. |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Document = await databases.decrementDocumentAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  documentId: '<DOCUMENT_ID>',
  attribute: '',
  value: 0,
  min: 0,
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.Document` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Document ID. |
| `sequence` | `number` | Document automatically incrementing ID. |
| `collectionId` | `string` | Collection ID. |
| `databaseId` | `string` | Database ID. |
| `createdAt` | `string` | Document creation date in ISO 8601 format. |
| `updatedAt` | `string` | Document update date in ISO 8601 format. |
| `permissions` | `string[]` | Document permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
