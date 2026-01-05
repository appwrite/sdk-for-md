# getAntivirus

Description: Check the Appwrite Antivirus server is up and connection is successful.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthAntivirus = await health.getAntivirus();
```

## Response Model

Returns a `Models.HealthAntivirus` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `version` | `string` | Antivirus version. |
| `status` | `HealthAntivirusStatus` | Antivirus status. Possible values are: `disabled`, `offline`, `online` |
