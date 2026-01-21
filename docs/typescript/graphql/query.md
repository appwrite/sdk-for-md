# query

Description: Execute a GraphQL mutation.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `query` | `object` | ✅ | The query or queries to execute. (Default: `{}`) |

## Usage

```typescript
import { Client, Graphql } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const graphql = new Graphql(client);
const result = await graphql.query({
  query: {},
});
```
