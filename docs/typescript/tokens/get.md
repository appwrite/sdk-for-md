# get

Description: Get a token by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `tokenId` | `string` | ✅ | Token ID. |

## Usage

```typescript
import { Client, Tokens, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tokens = new Tokens(client);
const result: Models.ResourceToken = await tokens.get({
  tokenId: '<TOKEN_ID>',
});
```

## Response Model

Returns a `Models.ResourceToken` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Token ID. |
| `createdAt` | `string` | Token creation date in ISO 8601 format. |
| `resourceId` | `string` | Resource ID. |
| `resourceType` | `string` | Resource type. |
| `expire` | `string` | Token expiration date in ISO 8601 format. |
| `secret` | `string` | JWT encoded string. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
