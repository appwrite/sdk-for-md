# listSuggestions

Description: List domain suggestions.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `query` | `string` | ✅ | Query to find available domains and suggestions. Max length: 256 chars. |
| `tlds` | `string[]` | ❌ | TLDs to suggest. (Default: `[]`) |
| `limit` | `number` | ❌ | Maximum number of suggestions to return. |
| `filterType` | `FilterType` | ❌ | Filter type: premium, suggestion.<br>**Allowed:** `premium`, `suggestion` |
| `priceMax` | `number` | ❌ | Filter premium domains by maximum price. Only premium domains at or below this price will be returned. Does not affect regular domain suggestions. |
| `priceMin` | `number` | ❌ | Filter premium domains by minimum price. Only premium domains at or above this price will be returned. Does not affect regular domain suggestions. |

## Usage

```typescript
import { Client, Domains, FilterType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainSuggestionsList = await domains.listSuggestions({
  query: '<QUERY>',
  tlds: [],
  limit: 0,
  filterType: FilterType.Premium,
  priceMax: 0,
  priceMin: 0,
});
```

## Response Model

Returns a `Models.DomainSuggestionsList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of suggestions that matched your query. |
| `suggestions` | `object[]` | List of suggestions. |
