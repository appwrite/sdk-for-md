# getFilePreview

Description: Get a file preview image. Currently, this method supports preview for image files (jpg, png, and gif), other supported formats, like pdf, docs, slides, and spreadsheets, will return the file icon image. You can also pass query string arguments for cutting and resizing your preview image. Preview is supported only for image files smaller than 10MB.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID |
| `width` | `number` | ❌ | Resize preview image width, Pass an integer between 0 to 4000. |
| `height` | `number` | ❌ | Resize preview image height, Pass an integer between 0 to 4000. |
| `gravity` | `ImageGravity` | ❌ | Image crop gravity. Can be one of center,top-left,top,top-right,left,right,bottom-left,bottom,bottom-right (Default: `center`)<br>**Allowed:** `center`, `top-left`, `top`, `top-right`, `left`, `right`, `bottom-left`, `bottom`, `bottom-right` |
| `quality` | `number` | ❌ | Preview image quality. Pass an integer between 0 to 100. Defaults to keep existing image quality. (Default: `-1`) |
| `borderWidth` | `number` | ❌ | Preview image border in pixels. Pass an integer between 0 to 100. Defaults to 0. |
| `borderColor` | `string` | ❌ | Preview image border color. Use a valid HEX color, no # is needed for prefix. |
| `borderRadius` | `number` | ❌ | Preview image border radius in pixels. Pass an integer between 0 to 4000. |
| `opacity` | `number` | ❌ | Preview image opacity. Only works with images having an alpha channel (like png). Pass a number between 0 to 1. (Default: `1`) |
| `rotation` | `number` | ❌ | Preview image rotation in degrees. Pass an integer between -360 and 360. |
| `background` | `string` | ❌ | Preview image background color. Only works with transparent images (png). Use a valid HEX color, no # is needed for prefix. |
| `output` | `ImageFormat` | ❌ | Output format type (jpeg, jpg, png, gif and webp).<br>**Allowed:** `jpg`, `jpeg`, `png`, `webp`, `heic`, `avif`, `gif` |
| `token` | `string` | ❌ | File token for accessing this file. |

## Usage

```typescript
import { Client, Storage, ImageGravity, ImageFormat } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result = storage.getFilePreview({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  width: 0,
  height: 0,
  gravity: ImageGravity.Center,
  quality: -1,
  borderWidth: 0,
  borderColor: '',
  borderRadius: 0,
  opacity: 0,
  rotation: -360,
  background: '',
  output: ImageFormat.Jpg,
  token: '<TOKEN>',
});
```
