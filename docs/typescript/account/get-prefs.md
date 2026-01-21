# getPrefs

Description: Get the preferences as a key-value object for the currently logged in user.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Preferences = await account.getPrefs();
```

## Response Model

Returns a `Models.Preferences` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
