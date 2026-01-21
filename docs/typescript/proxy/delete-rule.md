# deleteRule

Description: Delete a proxy rule by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `ruleId` | `string` | ✅ | Rule ID. |

## Usage

```typescript
import { Client, Proxy } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const proxy = new Proxy(client);
const result = await proxy.deleteRule({
  ruleId: '<RULE_ID>',
});
```
