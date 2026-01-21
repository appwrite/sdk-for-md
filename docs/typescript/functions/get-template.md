# getTemplate

Description: Get a function template using ID. You can use template details in [createFunction](/docs/references/cloud/server-nodejs/functions#create) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `templateId` | `string` | ✅ | Template ID. |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.TemplateFunction = await functions.getTemplate({
  templateId: '<TEMPLATE_ID>',
});
```

## Response Model

Returns a `Models.TemplateFunction` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `icon` | `string` | Function Template Icon. |
| `id` | `string` | Function Template ID. |
| `name` | `string` | Function Template Name. |
| `tagline` | `string` | Function Template Tagline. |
| `permissions` | `string[]` | Execution permissions. |
| `events` | `string[]` | Function trigger events. |
| `cron` | `string` | Function execution schedult in CRON format. |
| `timeout` | `number` | Function execution timeout in seconds. |
| `useCases` | `string[]` | Function use cases. |
| `runtimes` | `object[]` | List of runtimes that can be used with this template. |
| `instructions` | `string` | Function Template Instructions. |
| `vcsProvider` | `string` | VCS (Version Control System) Provider. |
| `providerRepositoryId` | `string` | VCS (Version Control System) Repository ID |
| `providerOwner` | `string` | VCS (Version Control System) Owner. |
| `providerVersion` | `string` | VCS (Version Control System) branch version (tag). |
| `variables` | `object[]` | Function variables. |
| `scopes` | `string[]` | Function scopes. |
