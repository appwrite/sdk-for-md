# createRelationshipAttribute

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createRelationshipColumn` instead

Description: Create relationship attribute. [Learn more about relationship attributes](https://appwrite.io/docs/databases-relationships#relationship-attributes).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `relatedCollectionId` | `string` | ✅ | Related Collection ID. |
| `type` | `RelationshipType` | ✅ | Relation type<br>**Allowed:** `oneToOne`, `manyToOne`, `manyToMany`, `oneToMany` |
| `twoWay` | `boolean` | ❌ | Is Two Way? |
| `key` | `string` | ❌ | Attribute Key. |
| `twoWayKey` | `string` | ❌ | Two Way Attribute Key. |
| `onDelete` | `RelationMutate` | ❌ | Constraints option (Default: `restrict`)<br>**Allowed:** `cascade`, `restrict`, `setNull` |

## Usage

```typescript
import { Client, Databases, RelationshipType, RelationMutate, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.AttributeRelationship = await databases.createRelationshipAttribute({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  relatedCollectionId: '<RELATED_COLLECTION_ID>',
  type: RelationshipType.OneToOne,
  twoWay: false,
  key: '',
  twoWayKey: '',
  onDelete: RelationMutate.Cascade,
});
```

## Response Model

Returns a `Models.AttributeRelationship` object with the following properties:

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
| `relatedCollection` | `string` | The ID of the related collection. |
| `relationType` | `string` | The type of the relationship. |
| `twoWay` | `boolean` | Is the relationship two-way? |
| `twoWayKey` | `string` | The key of the two-way relationship. |
| `onDelete` | `string` | How deleting the parent document will propagate to child documents. |
| `side` | `string` | Whether this is the parent or child side of the relationship |
