# createRecordMX

Description: Create a new MX record for the given domain. MX records are used to define the mail servers responsible 
    for accepting email messages for the domain. Multiple MX records can be created with different priorities.
    The priority parameter determines the order in which mail servers are used, with lower values indicating 
    higher priority.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `name` | `string` | ✅ | Record name (subdomain). |
| `value` | `string` | ✅ | Mail server domain for this MX record. |
| `ttl` | `number` | ✅ | Time to live, in seconds. Must be greater than 0. |
| `priority` | `number` | ✅ | MX priority. |
| `comment` | `string` | ❌ | A comment for this record. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DnsRecord = await domains.createRecordMX({
  domainId: '<DOMAIN_ID>',
  name: '<NAME>',
  value: '<VALUE>',
  ttl: 1,
  priority: 0,
  comment: '<COMMENT>',
});
```

## Response Model

Returns a `Models.DnsRecord` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | DNS Record ID. |
| `createdAt` | `string` | DNS Record creation time in ISO 8601 format. |
| `updatedAt` | `string` | DNS Record update date in ISO 8601 format. |
| `type` | `string` | DNS record type (e.g. A, CNAME, MX). |
| `name` | `string` | Record name or subdomain. |
| `value` | `string` | Value of the record (IP address, domain, etc.). |
| `ttl` | `number` | Time to live (in seconds). |
| `priority` | `number` | Record priority (commonly used for MX). |
| `lock` | `boolean` | Whether this record is locked (read-only). |
| `weight` | `number` | Record weight (used for SRV records). |
| `port` | `number` | Target port (used for SRV records). |
| `comment` | `string` | Comment for the DNS record. |
