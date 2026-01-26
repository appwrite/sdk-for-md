# createJWT

Description: Create a new JWT token. This token can be used to authenticate users with custom scopes and expiration time.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `scopes` | `string[]` | ✅ | List of scopes allowed for JWT key. Maximum of 100 scopes are allowed. |
| `duration` | `number` | ❌ | Time in seconds before JWT expires. Default duration is 900 seconds, and maximum is 3600 seconds. (Default: `900`) |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Jwt = await projects.createJWT({
  projectId: '<PROJECT_ID>',
  scopes: [],
  duration: 0,
});
```

## Response Model

Returns a `Models.Jwt` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `jwt` | `string` | JWT encoded string. |
