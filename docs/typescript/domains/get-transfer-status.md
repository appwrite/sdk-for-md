# getTransferStatus

Description: Retrieve the current transfer status for a domain. Returns the status, an optional reason, and a timestamp of the last status change.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainTransferStatus = await domains.getTransferStatus({
  domainId: '<DOMAIN_ID>',
});
```

## Response Model

Returns a `Models.DomainTransferStatus` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `status` | `DomainTransferStatusEnum` | Transfer status. |
| `reason` | `string` | Additional transfer status information. |
| `timestamp` | `string` | Transfer status timestamp in ISO 8601 format. |
