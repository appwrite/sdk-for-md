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
