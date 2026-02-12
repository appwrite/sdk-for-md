# listPolicies

Description: List all policies for a project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |

## Usage

```typescript
import { Client, Backups, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupPolicyList = await backups.listPolicies({
  queries: [],
});
```

## Response Model

Returns a `Models.BackupPolicyList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of policies that matched your query. |
| `policies` | `object[]` | List of policies. |
