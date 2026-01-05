# createOAuth2Token

Description: Allow the user to login to their account using the OAuth2 provider of their choice. Each OAuth2 provider should be enabled from the Appwrite console first. Use the success and failure arguments to provide a redirect URL&#039;s back to your app when login is completed. 

If authentication succeeds, `userId` and `secret` of a token will be appended to the success URL as query parameters. These can be used to create a new session using the [Create session](https://appwrite.io/docs/references/cloud/client-web/account#createSession) endpoint.

A user is limited to 10 active sessions at a time by default. [Learn more about session limits](https://appwrite.io/docs/authentication-security#limits).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `provider` | `OAuthProvider` | ✅ | OAuth2 Provider. Currently, supported providers are: amazon, apple, auth0, authentik, autodesk, bitbucket, bitly, box, dailymotion, discord, disqus, dropbox, etsy, facebook, figma, github, gitlab, google, linkedin, microsoft, notion, oidc, okta, paypal, paypalSandbox, podio, salesforce, slack, spotify, stripe, tradeshift, tradeshiftBox, twitch, wordpress, yahoo, yammer, yandex, zoho, zoom.<br>**Allowed:** `amazon`, `apple`, `auth0`, `authentik`, `autodesk`, `bitbucket`, `bitly`, `box`, `dailymotion`, `discord`, `disqus`, `dropbox`, `etsy`, `facebook`, `figma`, `github`, `gitlab`, `google`, `linkedin`, `microsoft`, `notion`, `oidc`, `okta`, `paypal`, `paypalSandbox`, `podio`, `salesforce`, `slack`, `spotify`, `stripe`, `tradeshift`, `tradeshiftBox`, `twitch`, `wordpress`, `yahoo`, `yammer`, `yandex`, `zoho`, `zoom`, `mock`, `mock-unverified` |
| `success` | `string` | ❌ | URL to redirect back to your app after a successful login attempt.  Only URLs from hostnames in your project&#039;s platform list are allowed. This requirement helps to prevent an [open redirect](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html) attack against your project API. |
| `failure` | `string` | ❌ | URL to redirect back to your app after a failed login attempt.  Only URLs from hostnames in your project&#039;s platform list are allowed. This requirement helps to prevent an [open redirect](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html) attack against your project API. |
| `scopes` | `string[]` | ❌ | A list of custom OAuth2 scopes. Check each provider internal docs for a list of supported scopes. Maximum of 100 scopes are allowed, each 4096 characters long. (Default: `[]`) |

## Usage

```typescript
import { Client, Account, OAuthProvider } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
account.createOAuth2Token({
  provider: OAuthProvider.Amazon,
  success: 'https://example.com',
  failure: 'https://example.com',
  scopes: [],
});
```
