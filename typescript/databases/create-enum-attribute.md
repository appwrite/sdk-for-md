# createEnumAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createEnumColumn` instead

Description: Create an enum attribute. The `elements` param acts as a white-list of accepted values for this attribute.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `key` | `string` | ✅ | Attribute Key. |
| `elements` | `string[]` | ✅ | Array of enum values. |
| `required` | `boolean` | ✅ | Is attribute required? |
| `default` | `string` | ❌ | Default value for attribute when not provided. Cannot be set when attribute is required. |
| `array` | `boolean` | ❌ | Is attribute an array? |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributeEnum = await databases.createEnumAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  elements: [],
  required: false,
  default: '<DEFAULT>',
  array: false,
});
```

## Response Model

Returns a `Models.AttributeEnum` object with the following properties:

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
| `elements` | `string[]` | Array of elements in enumerated type. |
| `format` | `string` | String format. |
| `default` | `string` | Default value for attribute when not provided. Cannot be set when attribute is required. |
