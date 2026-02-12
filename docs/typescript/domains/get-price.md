# getPrice

Description: Get the registration price for a domain name.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Domain name to get price for. |
| `periodYears` | `number` | ❌ | Number of years to calculate the domain price for. Must be at least 1. (Default: `1`) |
| `registrationType` | `RegistrationType` | ❌ | Type of registration pricing to fetch. Allowed values: new, transfer, renewal, trade. (Default: `new`)<br>**Allowed:** `new`, `transfer`, `renewal`, `trade` |

## Usage

```typescript
import { Client, Domains, RegistrationType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainPrice = await domains.getPrice({
  domain: '',
  periodYears: 0,
  registrationType: RegistrationType.New,
});
```

## Response Model

Returns a `Models.DomainPrice` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `domain` | `string` | Domain name. |
| `tld` | `string` | Top-level domain for the requested domain. |
| `available` | `boolean` | Whether the domain is currently available for registration. |
| `price` | `number` | Domain registration price. |
| `periodYears` | `number` | Price period in years. |
