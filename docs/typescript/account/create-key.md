# createKey

Description: Create a new account API key.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `name` | `string` | ✅ | Key name. Max length: 128 chars. |
| `scopes` | `Scopes` | ✅ | Key scopes list. Maximum of 100 scopes are allowed.<br>**Allowed:** `account`, `teams.read`, `teams.write` |
| `expire` | `string` | ❌ | Expiration time in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. Use null for unlimited expiration. |

## Usage

```typescript
import { Client, Account, Scopes, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Key = await account.createKey({
  name: '<NAME>',
  scopes: Scopes.Account,
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
