# getFlag

Description: You can use this endpoint to show different country flags icons to your users. The code argument receives the 2 letter country code. Use width, height and quality arguments to change the output settings. Country codes follow the [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1) standard.

When one dimension is specified and the other is 0, the image is scaled with preserved aspect ratio. If both dimensions are 0, the API provides an image at source quality. If dimensions are not specified, the default size of image returned is 100x100px.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `code` | `Flag` | ✅ | Country Code. ISO Alpha-2 country code format.<br>**Allowed:** `af`, `ao`, `al`, `ad`, `ae`, `ar`, `am`, `ag`, `au`, `at`, `az`, `bi`, `be`, `bj`, `bf`, `bd`, `bg`, `bh`, `bs`, `ba`, `by`, `bz`, `bo`, `br`, `bb`, `bn`, `bt`, `bw`, `cf`, `ca`, `ch`, `cl`, `cn`, `ci`, `cm`, `cd`, `cg`, `co`, `km`, `cv`, `cr`, `cu`, `cy`, `cz`, `de`, `dj`, `dm`, `dk`, `do`, `dz`, `ec`, `eg`, `er`, `es`, `ee`, `et`, `fi`, `fj`, `fr`, `fm`, `ga`, `gb`, `ge`, `gh`, `gn`, `gm`, `gw`, `gq`, `gr`, `gd`, `gt`, `gy`, `hn`, `hr`, `ht`, `hu`, `id`, `in`, `ie`, `ir`, `iq`, `is`, `il`, `it`, `jm`, `jo`, `jp`, `kz`, `ke`, `kg`, `kh`, `ki`, `kn`, `kr`, `kw`, `la`, `lb`, `lr`, `ly`, `lc`, `li`, `lk`, `ls`, `lt`, `lu`, `lv`, `ma`, `mc`, `md`, `mg`, `mv`, `mx`, `mh`, `mk`, `ml`, `mt`, `mm`, `me`, `mn`, `mz`, `mr`, `mu`, `mw`, `my`, `na`, `ne`, `ng`, `ni`, `nl`, `no`, `np`, `nr`, `nz`, `om`, `pk`, `pa`, `pe`, `ph`, `pw`, `pg`, `pl`, `pf`, `kp`, `pt`, `py`, `qa`, `ro`, `ru`, `rw`, `sa`, `sd`, `sn`, `sg`, `sb`, `sl`, `sv`, `sm`, `so`, `rs`, `ss`, `st`, `sr`, `sk`, `si`, `se`, `sz`, `sc`, `sy`, `td`, `tg`, `th`, `tj`, `tm`, `tl`, `to`, `tt`, `tn`, `tr`, `tv`, `tz`, `ug`, `ua`, `uy`, `us`, `uz`, `va`, `vc`, `ve`, `vn`, `vu`, `ws`, `ye`, `za`, `zm`, `zw` |
| `width` | `number` | ❌ | Image width. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `height` | `number` | ❌ | Image height. Pass an integer between 0 to 2000. Defaults to 100. (Default: `100`) |
| `quality` | `number` | ❌ | Image quality. Pass an integer between 0 to 100. Defaults to keep existing image quality. (Default: `-1`) |

## Usage

```typescript
import { Client, Avatars, Flag } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getFlag({
  code: Flag.Afghanistan,
  width: 0,
  height: 0,
  quality: -1,
});
```
