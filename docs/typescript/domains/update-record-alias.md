# updateRecordAlias

Description: Update an existing ALIAS record for the specified domain. This endpoint allows you to modify
    the properties of an existing ALIAS record including its name, target domain, TTL, and comment.
    
    The ALIAS record type is similar to a CNAME record but can be used at the zone apex (root domain).
    It provides a way to map one domain name to another.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `recordId` | `string` | ✅ | DNS record unique ID. |
| `name` | `string` | ✅ | Record name. |
| `value` | `string` | ✅ | Target domain for this ALIAS record. |
| `ttl` | `number` | ✅ | Time to live, in seconds. Must be greater than 0. |
| `comment` | `string` | ❌ | A comment for this record. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DnsRecord = await domains.updateRecordAlias({
  domainId: '<DOMAIN_ID>',
  recordId: '<RECORD_ID>',
  name: '<NAME>',
  value: '<VALUE>',
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
