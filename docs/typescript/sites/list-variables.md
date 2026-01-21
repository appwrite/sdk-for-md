# listVariables

Description: Get a list of all variables of a specific site.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site unique ID. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.VariableList = await sites.listVariables({
  siteId: '<SITE_ID>',
});
```

## Response Model

Returns a `Models.VariableList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of variables that matched your query. |
| `variables` | `object[]` | List of variables. |
