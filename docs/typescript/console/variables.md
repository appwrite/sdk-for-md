# variables

Description: Get all Environment Variables that are relevant for the console.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.ConsoleVariables = await console.variables();
```

## Response Model

Returns a `Models.ConsoleVariables` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `aPPDOMAINTARGETCNAME` | `string` | CNAME target for your Appwrite custom domains. |
| `aPPDOMAINTARGETA` | `string` | A target for your Appwrite custom domains. |
| `aPPCOMPUTEBUILDTIMEOUT` | `number` | Maximum build timeout in seconds. |
| `aPPDOMAINTARGETAAAA` | `string` | AAAA target for your Appwrite custom domains. |
| `aPPDOMAINTARGETCAA` | `string` | CAA target for your Appwrite custom domains. |
| `aPPSTORAGELIMIT` | `number` | Maximum file size allowed for file upload in bytes. |
| `aPPCOMPUTESIZELIMIT` | `number` | Maximum file size allowed for deployment in bytes. |
| `aPPUSAGESTATS` | `string` | Defines if usage stats are enabled. This value is set to &#039;enabled&#039; by default, to disable the usage stats set the value to &#039;disabled&#039;. |
| `aPPVCSENABLED` | `boolean` | Defines if VCS (Version Control System) is enabled. |
| `aPPDOMAINENABLED` | `boolean` | Defines if main domain is configured. If so, custom domains can be created. |
| `aPPASSISTANTENABLED` | `boolean` | Defines if AI assistant is enabled. |
| `aPPDOMAINSITES` | `string` | A comma separated list of domains to use for site URLs. |
| `aPPDOMAINFUNCTIONS` | `string` | A domain to use for function URLs. |
| `aPPOPTIONSFORCEHTTPS` | `string` | Defines if HTTPS is enforced for all requests. |
| `aPPDOMAINSNAMESERVERS` | `string` | Comma-separated list of nameservers. |
| `aPPDBADAPTER` | `string` | Database adapter in use. |
| `supportForRelationships` | `boolean` | Whether the database adapter supports relationships. |
| `supportForOperators` | `boolean` | Whether the database adapter supports operators. |
| `supportForSpatials` | `boolean` | Whether the database adapter supports spatial attributes. |
| `supportForSpatialIndexNull` | `boolean` | Whether the database adapter supports spatial indexes on nullable columns. |
| `supportForFulltextWildcard` | `boolean` | Whether the database adapter supports fulltext wildcard search. |
| `supportForMultipleFulltextIndexes` | `boolean` | Whether the database adapter supports multiple fulltext indexes per collection. |
| `supportForAttributeResizing` | `boolean` | Whether the database adapter supports resizing attributes. |
| `supportForSchemas` | `boolean` | Whether the database adapter supports fixed schemas with row width limits. |
| `maxIndexLength` | `number` | Maximum index length supported by the database adapter. |
| `supportForIntegerIds` | `boolean` | Whether the database adapter uses integer sequence IDs. |
