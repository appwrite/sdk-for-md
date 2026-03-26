# createSource

Description: Create a new source.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `ref` | `string` | ❌ | Ref param |
| `referrer` | `string` | ❌ | Referrer |
| `utmSource` | `string` | ❌ | Utm source |
| `utmCampaign` | `string` | ❌ | Utm campaign |
| `utmMedium` | `string` | ❌ | Utm medium |

## Usage

```typescript
import { Client, Console } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result = await console.createSource({
  ref: '<REF>',
  referrer: 'https://example.com',
  utmSource: '<UTM_SOURCE>',
  utmCampaign: '<UTM_CAMPAIGN>',
  utmMedium: '<UTM_MEDIUM>',
});
```
