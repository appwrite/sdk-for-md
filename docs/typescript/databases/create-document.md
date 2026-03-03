# createDocument

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createRow` instead

Description: Create a new Document. Before using this route, you should create a new collection resource using either a [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). Make sure to define attributes before creating documents. |
| `documentId` | `string` | ✅ | Document ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `data` | `object` | ✅ | Document data as JSON object. (Default: `{}`) |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, only the current user is granted all permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, Databases, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Document = await databases.createDocument({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  documentId: '<DOCUMENT_ID>',
  data: {
    "username": "walter.obrien",
    "email": "walter.obrien@example.com",
    "fullName": "Walter O'Brien",
    "age": 30,
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
