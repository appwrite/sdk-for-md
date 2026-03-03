# listEvents

Description: List all events for selected filters.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on attributes such as userId, teamId, etc. (Default: `[]`) |

## Usage

```typescript
import { Client, Activities, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const activities = new Activities(client);
const result: Models.ActivityEventList = await activities.listEvents({
  queries: '',
});
```

## Response Model

Returns a `Models.ActivityEventList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of events that matched your query. |
| `events` | `object[]` | List of events. |
