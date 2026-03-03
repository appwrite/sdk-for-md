# updateDocument

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.updateRow` instead

Description: Update a document by its unique ID. Using the patch method you can pass only specific fields that will get updated.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `documentId` | `string` | ✅ | Document ID. |
| `data` | `object` | ❌ | Document data as JSON object. Include only attribute and value pairs to be updated. (Default: `{}`) |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, the current permissions are inherited. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, Databases, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Document = await databases.updateDocument({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  documentId: '<DOCUMENT_ID>',
  data: {
    "username": "walter.obrien",
    "email": "walter.obrien@example.com",
    "fullName": "Walter O'Brien",
    "age": 33,
    "isAdmin": false
},
  permissions: [Permission.Read(Role.Any())],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.Document` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Document ID. |
| `sequence` | `number` | Document sequence ID. |
| `collectionId` | `string` | Collection ID. |
| `databaseId` | `string` | Database ID. |
| `createdAt` | `string` | Document creation date in ISO 8601 format. |
| `updatedAt` | `string` | Document update date in ISO 8601 format. |
| `permissions` | `string[]` | Document permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
