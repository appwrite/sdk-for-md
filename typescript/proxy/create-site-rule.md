# createSiteRule

Description: Create a new proxy rule for serving Appwrite Site on custom domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Domain name. |
| `siteId` | `string` | ✅ | ID of site to be executed. |
| `branch` | `string` | ❌ | Name of VCS branch to deploy changes automatically |

## Usage

```typescript
import { Client, Proxy, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const proxy = new Proxy(client);
const result: Models.ProxyRule = await proxy.createSiteRule({
  domain: '',
  siteId: '<SITE_ID>',
  branch: '<BRANCH>',
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
