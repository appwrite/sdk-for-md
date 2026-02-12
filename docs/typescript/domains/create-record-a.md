# createRecordA

Description: Create a new A record for the given domain. A records are used to point a domain name 
to an IPv4 address. The record value should be a valid IPv4 address.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `name` | `string` | ✅ | Record name (subdomain). |
| `value` | `string` | ✅ | IPv4 address for this A record. |
| `ttl` | `number` | ✅ | Time to live, in seconds. Must be greater than 0. |
| `comment` | `string` | ❌ | A comment explaining what this record is for. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DnsRecord = await domains.createRecordA({
  domainId: '<DOMAIN_ID>',
  name: '<NAME>',
  value: '',
  ttl: 1,
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
