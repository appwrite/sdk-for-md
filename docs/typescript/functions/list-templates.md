# listTemplates

Description: List available function templates. You can use template details in [createFunction](/docs/references/cloud/server-nodejs/functions#create) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `runtimes` | `Runtimes` | ❌ | List of runtimes allowed for filtering function templates. Maximum of 100 runtimes are allowed. (Default: `[]`)<br>**Allowed:** `node-14.5`, `node-16.0`, `node-18.0`, `node-19.0`, `node-20.0`, `node-21.0`, `node-22`, `node-23`, `node-24`, `node-25`, `php-8.0`, `php-8.1`, `php-8.2`, `php-8.3`, `php-8.4`, `ruby-3.0`, `ruby-3.1`, `ruby-3.2`, `ruby-3.3`, `ruby-3.4`, `ruby-4.0`, `python-3.8`, `python-3.9`, `python-3.10`, `python-3.11`, `python-3.12`, `python-3.13`, `python-3.14`, `python-ml-3.11`, `python-ml-3.12`, `python-ml-3.13`, `deno-1.40`, `deno-1.46`, `deno-2.0`, `deno-2.5`, `deno-2.6`, `dart-2.15`, `dart-2.16`, `dart-2.17`, `dart-2.18`, `dart-2.19`, `dart-3.0`, `dart-3.1`, `dart-3.3`, `dart-3.5`, `dart-3.8`, `dart-3.9`, `dart-3.10`, `dotnet-6.0`, `dotnet-7.0`, `dotnet-8.0`, `dotnet-10`, `java-8.0`, `java-11.0`, `java-17.0`, `java-18.0`, `java-21.0`, `java-22`, `java-25`, `swift-5.5`, `swift-5.8`, `swift-5.9`, `swift-5.10`, `swift-6.2`, `kotlin-1.6`, `kotlin-1.8`, `kotlin-1.9`, `kotlin-2.0`, `kotlin-2.3`, `cpp-17`, `cpp-20`, `bun-1.0`, `bun-1.1`, `bun-1.2`, `bun-1.3`, `go-1.23`, `go-1.24`, `go-1.25`, `go-1.26`, `static-1`, `flutter-3.24`, `flutter-3.27`, `flutter-3.29`, `flutter-3.32`, `flutter-3.35`, `flutter-3.38` |
| `useCases` | `UseCases` | ❌ | List of use cases allowed for filtering function templates. Maximum of 100 use cases are allowed. (Default: `[]`)<br>**Allowed:** `starter`, `databases`, `ai`, `messaging`, `utilities`, `dev-tools`, `auth` |
| `limit` | `number` | ❌ | Limit the number of templates returned in the response. Default limit is 25, and maximum limit is 5000. (Default: `25`) |
| `offset` | `number` | ❌ | Offset the list of returned templates. Maximum offset is 5000. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Functions, Runtimes, UseCases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.TemplateFunctionList = await functions.listTemplates({
  runtimes: Runtimes.Node145,
  useCases: UseCases.Starter,
  limit: 1,
  offset: 0,
  total: false,
});
```

## Response Model

Returns a `Models.TemplateFunctionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of templates that matched your query. |
| `templates` | `object[]` | List of templates. |
