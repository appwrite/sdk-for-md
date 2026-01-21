# updateFloatAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.updateFloatColumn` instead

Description: Update a float attribute. Changing the `default` value will not update already existing documents.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `key` | `string` | ✅ | Attribute Key. |
| `required` | `boolean` | ✅ | Is attribute required? |
| `default` | `number` | ✅ | Default value. Cannot be set when required. |
| `min` | `number` | ❌ | Minimum value. |
| `max` | `number` | ❌ | Maximum value. |
| `newKey` | `string` | ❌ | New Attribute Key. |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributeFloat = await databases.updateFloatAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  required: false,
  default: 0,
  min: 0,
  max: 0,
  newKey: '',
});
```

## Response Model

Returns a `Models.AttributeFloat` object with the following properties:

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
