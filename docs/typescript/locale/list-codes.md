# listCodes

Description: List of all locale codes in [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Locale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const locale = new Locale(client);
const result: Models.LocaleCodeList = await locale.listCodes();
```

## Response Model

Returns a `Models.LocaleCodeList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of localeCodes that matched your query. |
| `localeCodes` | `object[]` | List of localeCodes. |
