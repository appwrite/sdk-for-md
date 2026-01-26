# createRedirectRule

Description: Create a new proxy rule for to redirect from custom domain to another domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Domain name. |
| `url` | `string` | ✅ | Target URL of redirection |
| `statusCode` | `StatusCode` | ✅ | Status code of redirection<br>**Allowed:** `301`, `302`, `307`, `308` |
| `resourceId` | `string` | ✅ | ID of parent resource. |
| `resourceType` | `ProxyResourceType` | ✅ | Type of parent resource.<br>**Allowed:** `site`, `function` |

## Usage

```typescript
import { Client, Proxy, StatusCode, ProxyResourceType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const proxy = new Proxy(client);
const result: Models.ProxyRule = await proxy.createRedirectRule({
  domain: '',
  url: 'https://example.com',
  statusCode: StatusCode.MovedPermanently301,
  resourceId: '<RESOURCE_ID>',
  resourceType: ProxyResourceType.Site,
});
```

## Response Model

Returns a `Models.ProxyRule` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Rule ID. |
| `createdAt` | `string` | Rule creation date in ISO 8601 format. |
| `updatedAt` | `string` | Rule update date in ISO 8601 format. |
| `domain` | `string` | Domain name. |
| `type` | `string` | Action definition for the rule. Possible values are &quot;api&quot;, &quot;deployment&quot;, or &quot;redirect&quot; |
| `trigger` | `string` | Defines how the rule was created. Possible values are &quot;manual&quot; or &quot;deployment&quot; |
| `redirectUrl` | `string` | URL to redirect to. Used if type is &quot;redirect&quot; |
| `redirectStatusCode` | `number` | Status code to apply during redirect. Used if type is &quot;redirect&quot; |
| `deploymentId` | `string` | ID of deployment. Used if type is &quot;deployment&quot; |
| `deploymentResourceType` | `ProxyRuleDeploymentResourceType` | Type of deployment. Possible values are &quot;function&quot;, &quot;site&quot;. Used if rule&#039;s type is &quot;deployment&quot;. |
| `deploymentResourceId` | `string` | ID deployment&#039;s resource. Used if type is &quot;deployment&quot; |
| `deploymentVcsProviderBranch` | `string` | Name of Git branch that updates rule. Used if type is &quot;deployment&quot; |
| `status` | `ProxyRuleStatus` | Domain verification status. Possible values are &quot;created&quot;, &quot;verifying&quot;, &quot;verified&quot; and &quot;unverified&quot; |
| `logs` | `string` | Logs from rule verification or certificate generation. Certificate generation logs are prioritized if both are available. |
| `renewAt` | `string` | Certificate auto-renewal date in ISO 8601 format. |
