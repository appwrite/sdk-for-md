# get

Description: Get the current user location based on IP. Returns an object with user country code, country name, continent name, continent code, ip address and suggested currency. You can use the locale header to get the data in a supported language.

([IP Geolocation by DB-IP](https://db-ip.com))

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Locale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const locale = new Locale(client);
const result: Models.Locale = await locale.get();
```

## Response Model

Returns a `Models.Locale` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `ip` | `string` | User IP address. |
| `countryCode` | `string` | Country code in [ISO 3166-1](http://en.wikipedia.org/wiki/ISO_3166-1) two-character format |
| `country` | `string` | Country name. This field support localization. |
| `continentCode` | `string` | Continent code. A two character continent code &quot;AF&quot; for Africa, &quot;AN&quot; for Antarctica, &quot;AS&quot; for Asia, &quot;EU&quot; for Europe, &quot;NA&quot; for North America, &quot;OC&quot; for Oceania, and &quot;SA&quot; for South America. |
| `continent` | `string` | Continent name. This field support localization. |
| `eu` | `boolean` | True if country is part of the European Union. |
| `currency` | `string` | Currency code in [ISO 4217-1](http://en.wikipedia.org/wiki/ISO_4217) three-character format |
