# getInitials

Description: Use this endpoint to show your user initials avatar icon on your website or app. By default, this route will try to print your logged-in user name or email initials. You can also overwrite the user name if you pass the &#039;name&#039; parameter. If no name is given and no user is logged, an empty avatar will be returned.

You can use the color and background params to change the avatar colors. By default, a random theme will be selected. The random theme will persist for the user&#039;s initials when reloading the same theme will always return for the same initials.

When one dimension is specified and the other is 0, the image is scaled with preserved aspect ratio. If both dimensions are 0, the API provides an image at source quality. If dimensions are not specified, the default size of image returned is 100x100px.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `name` | `string` | ❌ | Full Name. When empty, current user name or email will be used. Max length: 128 chars. |
| `width` | `number` | ❌ | Image width. Pass an integer between 0 to 2000. Defaults to 100. (Default: `500`) |
| `height` | `number` | ❌ | Image height. Pass an integer between 0 to 2000. Defaults to 100. (Default: `500`) |
| `background` | `string` | ❌ | Changes background color. By default a random color will be picked and stay will persistent to the given name. |

## Usage

```typescript
import { Client, Avatars } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getInitials({
  name: '<NAME>',
  width: 0,
  height: 0,
  background: '',
});
```
