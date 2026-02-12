# getProgram

Description: Receive the details of a program using its ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `programId` | `string` | ✅ | ID of the program |

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.Program = await console.getProgram({
  programId: '<PROGRAM_ID>',
});
```

## Response Model

Returns a `Models.Program` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Program ID |
| `title` | `string` | Program title |
| `description` | `string` | Program description |
| `tag` | `string` | Program tag for highlighting on console |
| `icon` | `string` | Program icon for highlighting on console |
| `url` | `string` | URL for more information on this program |
| `active` | `boolean` | Whether this program is active |
| `external` | `boolean` | Whether this program is external |
| `billingPlanId` | `string` | Billing plan ID that this is program is associated with. |
