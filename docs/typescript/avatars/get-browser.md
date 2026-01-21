# getBrowser

Description: You can use this endpoint to show different browser icons to your users. The code argument receives the browser code as it appears in your user [GET /account/sessions](https://appwrite.io/docs/references/cloud/client-web/account#getSessions) endpoint. Use width, height and quality arguments to change the output settings.

When one dimension is specified and the other is 0, the image is scaled with preserved aspect ratio. If both dimensions are 0, the API provides an image at source quality. If dimensions are not specified, the default size of image returned is 100x100px.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `code` | `Browser` | ✅ | Browser Code.<br>**Allowed:** `aa`, `an`, `ch`, `ci`, `cm`, `cr`, `ff`, `sf`, `mf`, `ps`, `oi`, `om`, `op`, `on` |
| `width` | `number` | ❌ | Image width. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `height` | `number` | ❌ | Image height. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `quality` | `number` | ❌ | Image quality. Pass an integer between 0 to 100. Defaults to keep existing image quality. (Default: `-1`) |

## Usage

```typescript
import { Client, Avatars, Browser } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getBrowser({
  code: Browser.AvantBrowser,
  width: 0,
  height: 0,
  quality: -1,
});
```
