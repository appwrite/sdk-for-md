# getKey

Description: Get a key by its unique ID. This endpoint returns details about a specific API key in your project including it&#039;s scopes.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `keyId` | `string` | ✅ | Key unique ID. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Key = await projects.getKey({
  projectId: '<PROJECT_ID>',
  keyId: '<KEY_ID>',
});
```

## Response Model

Returns a `Models.Key` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Key ID. |
| `createdAt` | `string` | Key creation date in ISO 8601 format. |
| `updatedAt` | `string` | Key update date in ISO 8601 format. |
| `name` | `string` | Key name. |
| `expire` | `string` | Key expiration date in ISO 8601 format. |
| `scopes` | `string[]` | Allowed permission scopes. |
| `secret` | `string` | Secret key. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
| `sdks` | `string[]` | List of SDK user agents that used this key. |
