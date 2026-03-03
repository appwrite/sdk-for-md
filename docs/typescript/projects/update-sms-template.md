# updateSMSTemplate

Description: Update a custom SMS template for the specified locale and type. Use this endpoint to modify the content of your SMS templates.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `type` | `SmsTemplateType` | ✅ | Template type<br>**Allowed:** `verification`, `login`, `invitation`, `mfaChallenge` |
| `locale` | `SmsTemplateLocale` | ✅ | Template locale<br>**Allowed:** `af`, `ar-ae`, `ar-bh`, `ar-dz`, `ar-eg`, `ar-iq`, `ar-jo`, `ar-kw`, `ar-lb`, `ar-ly`, `ar-ma`, `ar-om`, `ar-qa`, `ar-sa`, `ar-sy`, `ar-tn`, `ar-ye`, `as`, `az`, `be`, `bg`, `bh`, `bn`, `bs`, `ca`, `cs`, `cy`, `da`, `de`, `de-at`, `de-ch`, `de-li`, `de-lu`, `el`, `en`, `en-au`, `en-bz`, `en-ca`, `en-gb`, `en-ie`, `en-jm`, `en-nz`, `en-tt`, `en-us`, `en-za`, `eo`, `es`, `es-ar`, `es-bo`, `es-cl`, `es-co`, `es-cr`, `es-do`, `es-ec`, `es-gt`, `es-hn`, `es-mx`, `es-ni`, `es-pa`, `es-pe`, `es-pr`, `es-py`, `es-sv`, `es-uy`, `es-ve`, `et`, `eu`, `fa`, `fi`, `fo`, `fr`, `fr-be`, `fr-ca`, `fr-ch`, `fr-lu`, `ga`, `gd`, `he`, `hi`, `hr`, `hu`, `id`, `is`, `it`, `it-ch`, `ja`, `ji`, `ko`, `ku`, `lt`, `lv`, `mk`, `ml`, `ms`, `mt`, `nb`, `ne`, `nl`, `nl-be`, `nn`, `no`, `pa`, `pl`, `pt`, `pt-br`, `rm`, `ro`, `ro-md`, `ru`, `ru-md`, `sb`, `sk`, `sl`, `sq`, `sr`, `sv`, `sv-fi`, `th`, `tn`, `tr`, `ts`, `ua`, `ur`, `ve`, `vi`, `xh`, `zh-cn`, `zh-hk`, `zh-sg`, `zh-tw`, `zu` |
| `message` | `string` | ✅ | Template message |

## Usage

```typescript
import { Client, Projects, SmsTemplateType, SmsTemplateLocale, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.SmsTemplate = await projects.updateSMSTemplate({
  projectId: '<PROJECT_ID>',
  type: SmsTemplateType.Verification,
  locale: SmsTemplateLocale.Af,
  message: '<MESSAGE>',
});
```

## Response Model

Returns a `Models.SmsTemplate` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `type` | `string` | Template type |
| `locale` | `string` | Template locale |
| `message` | `string` | Template message |
