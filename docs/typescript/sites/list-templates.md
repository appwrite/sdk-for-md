# listTemplates

Description: List available site templates. You can use template details in [createSite](/docs/references/cloud/server-nodejs/sites#create) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `frameworks` | `Frameworks` | ❌ | List of frameworks allowed for filtering site templates. Maximum of 100 frameworks are allowed. (Default: `[]`)<br>**Allowed:** `analog`, `angular`, `nextjs`, `react`, `nuxt`, `vue`, `sveltekit`, `astro`, `tanstack-start`, `remix`, `lynx`, `flutter`, `react-native`, `vite`, `other` |
| `useCases` | `UseCases` | ❌ | List of use cases allowed for filtering site templates. Maximum of 100 use cases are allowed. (Default: `[]`)<br>**Allowed:** `dev-tools`, `starter`, `databases`, `ai`, `messaging`, `utilities` |
| `limit` | `number` | ❌ | Limit the number of templates returned in the response. Default limit is 25, and maximum limit is 5000. (Default: `25`) |
| `offset` | `number` | ❌ | Offset the list of returned templates. Maximum offset is 5000. |

## Usage

```typescript
import { Client, Sites, Frameworks, UseCases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.TemplateSiteList = await sites.listTemplates({
  frameworks: Frameworks.Analog,
  useCases: UseCases.DevTools,
  limit: 1,
  offset: 0,
});
```

## Response Model

Returns a `Models.TemplateSiteList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of templates that matched your query. |
| `templates` | `object[]` | List of templates. |
