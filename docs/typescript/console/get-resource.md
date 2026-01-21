# getResource

Description: Check if a resource ID is available.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `value` | `string` | ✅ | Resource value. |
| `type` | `ConsoleResourceType` | ✅ | Resource type.<br>**Allowed:** `rules` |

## Usage

```typescript
import { Client, Console, ConsoleResourceType } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result = await console.getResource({
  value: '<VALUE>',
  type: ConsoleResourceType.Rules,
});
```
