# getImage

Description: Use this endpoint to fetch a remote image URL and crop it to any image size you want. This endpoint is very useful if you need to crop and display remote images in your app or in case you want to make sure a 3rd party image is properly served using a TLS protocol.

When one dimension is specified and the other is 0, the image is scaled with preserved aspect ratio. If both dimensions are 0, the API provides an image at source quality. If dimensions are not specified, the default size of image returned is 400x400px.

This endpoint does not follow HTTP redirects.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `url` | `string` | ✅ | Image URL which you want to crop. |
| `width` | `number` | ❌ | Resize preview image width, Pass an integer between 0 to 2000. Defaults to 400. (Default: `400`) |
| `height` | `number` | ❌ | Resize preview image height, Pass an integer between 0 to 2000. Defaults to 400. (Default: `400`) |

## Usage

```typescript
import { Client, Avatars } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getImage({
  url: 'https://example.com',
  width: 0,
  height: 0,
});
```
