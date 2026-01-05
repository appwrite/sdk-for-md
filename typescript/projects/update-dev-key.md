# updateDevKey

Description: Update a project\&#039;s dev key by its unique ID. Use this endpoint to update a project\&#039;s dev key name or expiration time.&#039;

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `keyId` | `string` | ✅ | Key unique ID. |
| `name` | `string` | ✅ | Key name. Max length: 128 chars. |
| `expire` | `string` | ✅ | Expiration time in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.DevKey = await projects.updateDevKey({
  projectId: '<PROJECT_ID>',
  keyId: '<KEY_ID>',
  name: '<NAME>',
  expire: '',
});
```

## Response Model

Returns a `Models.DevKey` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Key ID. |
| `createdAt` | `string` | Key creation date in ISO 8601 format. |
| `updatedAt` | `string` | Key update date in ISO 8601 format. |
| `name` | `string` | Key name. |
| `expire` | `string` | Key expiration date in ISO 8601 format. |
| `secret` | `string` | Secret key. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
| `sdks` | `string[]` | List of SDK user agents that used this key. |
