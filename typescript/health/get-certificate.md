# getCertificate

Description: Get the SSL certificate for a domain

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ❌ | string |

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthCertificate = await health.getCertificate({
  domain: '',
});
```

## Response Model

Returns a `Models.HealthCertificate` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `name` | `string` | Certificate name |
| `subjectSN` | `string` | Subject SN |
| `issuerOrganisation` | `string` | Issuer organisation |
| `validFrom` | `string` | Valid from |
| `validTo` | `string` | Valid to |
| `signatureTypeSN` | `string` | Signature type SN |
