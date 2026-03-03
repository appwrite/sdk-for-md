# getScopes

Description: Get Scopes

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization id |
| `projectId` | `string` | ❌ | Project id |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.Roles = await organizations.getScopes({
  organizationId: '<ORGANIZATION_ID>',
  projectId: '<PROJECT_ID>',
});
```

## Response Model

Returns a `Models.Roles` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `scopes` | `string[]` | Array of scopes accessible to current user. |
| `roles` | `string[]` | Array of roles assigned to current user. |
