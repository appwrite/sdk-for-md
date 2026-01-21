# getTime

Description: Check the Appwrite server time is synced with Google remote NTP server. We use this technology to smoothly handle leap seconds with no disruptive events. The [Network Time Protocol](https://en.wikipedia.org/wiki/Network_Time_Protocol) (NTP) is used by hundreds of millions of computers and devices to synchronize their clocks over the Internet. If your computer sets its own clock, it likely uses NTP.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthTime = await health.getTime();
```

## Response Model

Returns a `Models.HealthTime` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `remoteTime` | `number` | Current unix timestamp on trustful remote server. |
| `localTime` | `number` | Current unix timestamp of local server where Appwrite runs. |
| `diff` | `number` | Difference of unix remote and local timestamps in milliseconds. |
