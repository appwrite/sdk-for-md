# createSchedule

Description: Create a new schedule for a resource.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `resourceType` | `ResourceType` | ✅ | The resource type for the schedule. Possible values: function, execution, message, backup.<br>**Allowed:** `function`, `execution`, `message`, `backup` |
| `resourceId` | `string` | ✅ | The resource ID to associate with this schedule. |
| `schedule` | `string` | ✅ | Schedule CRON expression. |
| `active` | `boolean` | ❌ | Whether the schedule is active. |
| `data` | `object` | ❌ | Schedule data as a JSON string. Used to store resource-specific context needed for execution. (Default: `{}`) |

## Usage

```typescript
import { Client, Projects, ResourceType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Schedule = await projects.createSchedule({
  projectId: '<PROJECT_ID>',
  resourceType: ResourceType.Function,
  resourceId: '<RESOURCE_ID>',
  schedule: '',
  active: false,
  data: {},
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
