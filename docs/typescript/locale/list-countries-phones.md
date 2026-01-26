# listCountriesPhones

Description: List of all countries phone codes. You can use the locale header to get the data in a supported language.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Locale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const locale = new Locale(client);
const result: Models.PhoneList = await locale.listCountriesPhones();
```

## Response Model

Returns a `Models.PhoneList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of phones that matched your query. |
| `phones` | `object[]` | List of phones. |
