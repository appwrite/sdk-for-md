# listSpecifications

Description: List allowed site specifications for this instance.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.SpecificationList = await sites.listSpecifications();
```

## Response Model

Returns a `Models.SpecificationList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of specifications that matched your query. |
| `specifications` | `object[]` | List of specifications. |
