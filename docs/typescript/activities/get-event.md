# getEvent

Description: Get event by ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `eventId` | `string` | ✅ | Event ID. |

## Usage

```typescript
import { Client, Activities, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const activities = new Activities(client);
const result: Models.ActivityEvent = await activities.getEvent({
  eventId: '<EVENT_ID>',
});
```

## Response Model

Returns a `Models.ActivityEvent` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Event ID. |
| `userType` | `string` | User type. |
| `userId` | `string` | User ID. |
| `userEmail` | `string` | User Email. |
| `userName` | `string` | User Name. |
| `resourceParent` | `string` | Resource parent. |
| `resourceType` | `string` | Resource type. |
| `resourceId` | `string` | Resource ID. |
| `resource` | `string` | Resource. |
| `event` | `string` | Event name. |
| `userAgent` | `string` | User agent. |
| `ip` | `string` | IP address. |
| `mode` | `string` | API mode when event triggered. |
| `country` | `string` | Location. |
| `time` | `string` | Log creation date in ISO 8601 format. |
| `projectId` | `string` | Project ID. |
| `teamId` | `string` | Team ID. |
| `hostname` | `string` | Hostname. |
| `osCode` | `string` | Operating system code name. View list of [available options](https://github.com/appwrite/appwrite/blob/master/docs/lists/os.json). |
| `osName` | `string` | Operating system name. |
| `osVersion` | `string` | Operating system version. |
| `clientType` | `string` | Client type. |
| `clientCode` | `string` | Client code name. View list of [available options](https://github.com/appwrite/appwrite/blob/master/docs/lists/clients.json). |
| `clientName` | `string` | Client name. |
| `clientVersion` | `string` | Client version. |
| `clientEngine` | `string` | Client engine name. |
| `clientEngineVersion` | `string` | Client engine name. |
| `deviceName` | `string` | Device name. |
| `deviceBrand` | `string` | Device brand name. |
| `deviceModel` | `string` | Device model name. |
| `countryCode` | `string` | Country two-character ISO 3166-1 alpha code. |
| `countryName` | `string` | Country name. |
