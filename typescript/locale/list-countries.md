# listCountries

Description: List of all countries. You can use the locale header to get the data in a supported language.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Locale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const locale = new Locale(client);
const result: Models.CountryList = await locale.listCountries();
```

## Response Model

Returns a `Models.CountryList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of countries that matched your query. |
| `countries` | `object[]` | List of countries. |
