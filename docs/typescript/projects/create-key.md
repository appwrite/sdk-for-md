# createKey

Description: Create a new API key. It&#039;s recommended to have multiple API keys with strict scopes for separate functions within your project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `name` | `string` | ✅ | Key name. Max length: 128 chars. |
| `scopes` | `Scopes` | ✅ | Key scopes list. Maximum of 100 scopes are allowed.<br>**Allowed:** `sessions.write`, `users.read`, `users.write`, `teams.read`, `teams.write`, `databases.read`, `databases.write`, `collections.read`, `collections.write`, `tables.read`, `tables.write`, `attributes.read`, `attributes.write`, `columns.read`, `columns.write`, `indexes.read`, `indexes.write`, `documents.read`, `documents.write`, `rows.read`, `rows.write`, `files.read`, `files.write`, `buckets.read`, `buckets.write`, `functions.read`, `functions.write`, `sites.read`, `sites.write`, `log.read`, `log.write`, `execution.read`, `execution.write`, `locale.read`, `avatars.read`, `health.read`, `providers.read`, `providers.write`, `messages.read`, `messages.write`, `topics.read`, `topics.write`, `subscribers.read`, `subscribers.write`, `targets.read`, `targets.write`, `rules.read`, `rules.write`, `migrations.read`, `migrations.write`, `vcs.read`, `vcs.write`, `assistant.read`, `tokens.read`, `tokens.write`, `policies.write`, `policies.read`, `archives.read`, `archives.write`, `restorations.read`, `restorations.write`, `domains.read`, `domains.write` |
| `keyId` | `string` | ❌ | Key ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. (Default: `unique()`) |
| `expire` | `string` | ❌ | Expiration time in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. Use null for unlimited expiration. |

## Usage

```typescript
import { Client, Projects, Scopes, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Key = await projects.createKey({
  projectId: '<PROJECT_ID>',
  name: '<NAME>',
  scopes: Scopes.SessionsWrite,
  keyId: '<KEY_ID>',
  expire: '',
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
