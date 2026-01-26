# createEmailAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createEmailColumn` instead

Description: Create an email attribute.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `key` | `string` | ✅ | Attribute Key. |
| `required` | `boolean` | ✅ | Is attribute required? |
| `default` | `string` | ❌ | Default value for attribute when not provided. Cannot be set when attribute is required. |
| `array` | `boolean` | ❌ | Is attribute an array? |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributeEmail = await databases.createEmailAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
  required: false,
  default: 'email@example.com',
  array: false,
});
```

## Response Model

Returns a `Models.AttributeEmail` object with the following properties:

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
| `format` | `string` | String format. |
| `default` | `string` | Default value for attribute when not provided. Cannot be set when attribute is required. |
