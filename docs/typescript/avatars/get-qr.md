# getQR

Description: Converts a given plain text to a QR code image. You can use the query parameters to change the size and style of the resulting image.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `text` | `string` | ✅ | Plain text to be converted to QR code image. |
| `size` | `number` | ❌ | QR code size. Pass an integer between 1 to 1000. Defaults to 400. (Default: `400`) |
| `margin` | `number` | ❌ | Margin from edge. Pass an integer between 0 to 10. Defaults to 1. (Default: `1`) |
| `download` | `boolean` | ❌ | Return resulting image with &#039;Content-Disposition: attachment &#039; headers for the browser to start downloading it. Pass 0 for no header, or 1 for otherwise. Default value is set to 0. |

## Usage

```typescript
import { Client, Avatars } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getQR({
  text: '<TEXT>',
  size: 1,
  margin: 0,
  download: false,
});
```
