# listSessions

Description: Get the list of active sessions across different devices for the currently logged in user.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.SessionList = await account.listSessions();
```

## Response Model

Returns a `Models.SessionList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of sessions that matched your query. |
| `sessions` | `object[]` | List of sessions. |
