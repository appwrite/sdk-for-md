# delete

Description: Delete a token by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `tokenId` | `string` | ✅ | Token ID. |

## Usage

```typescript
import { Client, Tokens } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tokens = new Tokens(client);
const result = await tokens.delete({
  tokenId: '<TOKEN_ID>',
});
```
