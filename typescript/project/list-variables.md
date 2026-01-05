# listVariables

Description: Get a list of all project variables. These variables will be accessible in all Appwrite Functions at runtime.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Project, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const project = new Project(client);
const result: Models.VariableList = await project.listVariables();
```

## Response Model

Returns a `Models.VariableList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of variables that matched your query. |
| `variables` | `object[]` | List of variables. |
