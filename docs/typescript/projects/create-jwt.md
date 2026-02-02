# createJWT

Description: Create a new JWT token. This token can be used to authenticate users with custom scopes and expiration time.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `scopes` | `Scopes` | ✅ | List of scopes allowed for JWT key. Maximum of 100 scopes are allowed.<br>**Allowed:** `sessions.write`, `users.read`, `users.write`, `teams.read`, `teams.write`, `databases.read`, `databases.write`, `collections.read`, `collections.write`, `tables.read`, `tables.write`, `attributes.read`, `attributes.write`, `columns.read`, `columns.write`, `indexes.read`, `indexes.write`, `documents.read`, `documents.write`, `rows.read`, `rows.write`, `files.read`, `files.write`, `buckets.read`, `buckets.write`, `functions.read`, `functions.write`, `sites.read`, `sites.write`, `log.read`, `log.write`, `execution.read`, `execution.write`, `locale.read`, `avatars.read`, `health.read`, `providers.read`, `providers.write`, `messages.read`, `messages.write`, `topics.read`, `topics.write`, `subscribers.read`, `subscribers.write`, `targets.read`, `targets.write`, `rules.read`, `rules.write`, `migrations.read`, `migrations.write`, `vcs.read`, `vcs.write`, `assistant.read`, `tokens.read`, `tokens.write` |
| `duration` | `number` | ❌ | Time in seconds before JWT expires. Default duration is 900 seconds, and maximum is 3600 seconds. (Default: `900`) |

## Usage

```typescript
import { Client, Projects, Scopes, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Jwt = await projects.createJWT({
  projectId: '<PROJECT_ID>',
  scopes: Scopes.SessionsWrite,
  duration: 0,
});
```

## Response Model

Returns a `Models.Jwt` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `jwt` | `string` | JWT encoded string. |
