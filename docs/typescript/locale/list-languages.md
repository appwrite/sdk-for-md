# listLanguages

Description: List of all languages classified by ISO 639-1 including 2-letter code, name in English, and name in the respective language.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Locale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const locale = new Locale(client);
const result: Models.LanguageList = await locale.listLanguages();
```

## Response Model

Returns a `Models.LanguageList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of languages that matched your query. |
| `languages` | `object[]` | List of languages. |
