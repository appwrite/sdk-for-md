# createIntegerAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createIntegerColumn` instead

Description: Create an integer attribute. Optionally, minimum and maximum values can be provided.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `key` | `string` | ✅ | Attribute Key. |
| `required` | `boolean` | ✅ | Is attribute required? |
| `min` | `number` | ❌ | Minimum value |
| `max` | `number` | ❌ | Maximum value |
| `default` | `number` | ❌ | Default value. Cannot be set when attribute is required. |
| `array` | `boolean` | ❌ | Is attribute an array? |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributeInteger = await databases.createIntegerAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  required: false,
  min: 0,
  max: 0,
  default: 0,
  array: false,
});
```

## Response Model

Returns a `Models.AttributeInteger` object with the following properties:

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
| `min` | `number` | Minimum value to enforce for new documents. |
| `max` | `number` | Maximum value to enforce for new documents. |
| `default` | `number` | Default value for attribute when not provided. Cannot be set when attribute is required. |
