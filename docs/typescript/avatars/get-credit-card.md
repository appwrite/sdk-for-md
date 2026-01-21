# getCreditCard

Description: The credit card endpoint will return you the icon of the credit card provider you need. Use width, height and quality arguments to change the output settings.

When one dimension is specified and the other is 0, the image is scaled with preserved aspect ratio. If both dimensions are 0, the API provides an image at source quality. If dimensions are not specified, the default size of image returned is 100x100px.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `code` | `CreditCard` | ✅ | Credit Card Code. Possible values: amex, argencard, cabal, cencosud, diners, discover, elo, hipercard, jcb, mastercard, naranja, targeta-shopping, unionpay, visa, mir, maestro, rupay.<br>**Allowed:** `amex`, `argencard`, `cabal`, `cencosud`, `diners`, `discover`, `elo`, `hipercard`, `jcb`, `mastercard`, `naranja`, `targeta-shopping`, `unionpay`, `visa`, `mir`, `maestro`, `rupay` |
| `width` | `number` | ❌ | Image width. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `height` | `number` | ❌ | Image height. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `quality` | `number` | ❌ | Image quality. Pass an integer between 0 to 100. Defaults to keep existing image quality. (Default: `-1`) |

## Usage

```typescript
import { Client, Avatars, CreditCard } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getCreditCard({
  code: CreditCard.AmericanExpress,
  width: 0,
  height: 0,
  quality: -1,
});
```
