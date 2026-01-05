# getFavicon

Description: Use this endpoint to fetch the favorite icon (AKA favicon) of any remote website URL.

This endpoint does not follow HTTP redirects.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `url` | `string` | ✅ | Website URL which you want to fetch the favicon from. |

## Usage

```typescript
import { Client, Avatars } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getFavicon({
  url: 'https://example.com',
});
```
