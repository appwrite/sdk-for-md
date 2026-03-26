# getSchedule

Description: Get a schedule by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `scheduleId` | `string` | ✅ | Schedule ID. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Schedule = await projects.getSchedule({
  projectId: '<PROJECT_ID>',
  scheduleId: '<SCHEDULE_ID>',
});
```

## Response Model

Returns a `Models.Schedule` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Schedule ID. |
| `createdAt` | `string` | Schedule creation date in ISO 8601 format. |
| `updatedAt` | `string` | Schedule update date in ISO 8601 format. |
| `resourceType` | `string` | The resource type associated with this schedule. |
| `resourceId` | `string` | The resource ID associated with this schedule. |
| `resourceUpdatedAt` | `string` | Change-tracking timestamp used by the scheduler to detect resource changes in ISO 8601 format. |
| `projectId` | `string` | The project ID associated with this schedule. |
| `schedule` | `string` | The CRON schedule expression. |
| `data` | `object` | Schedule data used to store resource-specific context needed for execution. |
| `active` | `boolean` | Whether the schedule is active. |
| `region` | `string` | The region where the schedule is deployed. |
