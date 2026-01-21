# delete

Description: Delete the currently logged in user.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.delete();
```
