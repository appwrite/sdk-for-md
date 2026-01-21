# deleteSessions

Description: Delete all sessions from the user account and remove any sessions cookies from the end client.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deleteSessions();
```
