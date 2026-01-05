# getTemplate

Description: Get a site template using ID. You can use template details in [createSite](/docs/references/cloud/server-nodejs/sites#create) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `templateId` | `string` | ✅ | Template ID. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.TemplateSite = await sites.getTemplate({
  templateId: '<TEMPLATE_ID>',
});
```

## Response Model

Returns a `Models.TemplateSite` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `key` | `string` | Site Template ID. |
| `name` | `string` | Site Template Name. |
| `tagline` | `string` | Short description of template |
| `demoUrl` | `string` | URL hosting a template demo. |
| `screenshotDark` | `string` | File URL with preview screenshot in dark theme preference. |
| `screenshotLight` | `string` | File URL with preview screenshot in light theme preference. |
| `useCases` | `string[]` | Site use cases. |
| `frameworks` | `object[]` | List of frameworks that can be used with this template. |
| `vcsProvider` | `string` | VCS (Version Control System) Provider. |
| `providerRepositoryId` | `string` | VCS (Version Control System) Repository ID |
| `providerOwner` | `string` | VCS (Version Control System) Owner. |
| `providerVersion` | `string` | VCS (Version Control System) branch version (tag). |
| `variables` | `object[]` | Site variables. |
