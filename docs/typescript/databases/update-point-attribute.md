# updatePointAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.updatePointColumn` instead

Description: Update a point attribute. Changing the `default` value will not update already existing documents.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#createCollection). |
| `key` | `string` | ✅ | Attribute Key. |
| `required` | `boolean` | ✅ | Is attribute required? |
| `default` | `any[]` | ❌ | Default value for attribute when not provided, array of two numbers [longitude, latitude], representing a single coordinate. Cannot be set when attribute is required. |
| `newKey` | `string` | ❌ | New attribute key. |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributePoint = await databases.updatePointAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  required: false,
  default: [1, 2],
  newKey: '',
});
```

## Response Model

Returns a `Models.AttributePoint` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `key` | `string` | Attribute Key. |
| `type` | `string` | Attribute type. |
| `status` | `AttributeStatus` | Attribute status. Possible values: `available`, `processing`, `deleting`, `stuck`, or `failed` |
| `error` | `string` | Error message. Displays error generated on failure of creating or deleting an attribute. |
| `required` | `boolean` | Is attribute required? |
| `array` | `boolean` | Is attribute an array? |
| `createdAt` | `string` | Attribute creation date in ISO 8601 format. |
| `updatedAt` | `string` | Attribute update date in ISO 8601 format. |
| `default` | `any[]` | Default value for attribute when not provided. Cannot be set when attribute is required. |
