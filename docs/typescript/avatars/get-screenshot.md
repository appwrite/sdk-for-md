# getScreenshot

Description: Use this endpoint to capture a screenshot of any website URL. This endpoint uses a headless browser to render the webpage and capture it as an image.

You can configure the browser viewport size, theme, user agent, geolocation, permissions, and more. Capture either just the viewport or the full page scroll.

When width and height are specified, the image is resized accordingly. If both dimensions are 0, the API provides an image at original size. If dimensions are not specified, the default viewport size is 1280x720px.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `url` | `string` | ✅ | Website URL which you want to capture. |
| `headers` | `object` | ❌ | HTTP headers to send with the browser request. Defaults to empty. (Default: `{}`) |
| `viewportWidth` | `number` | ❌ | Browser viewport width. Pass an integer between 1 to 1920. Defaults to 1280. (Default: `1280`) |
| `viewportHeight` | `number` | ❌ | Browser viewport height. Pass an integer between 1 to 1080. Defaults to 720. (Default: `720`) |
| `scale` | `number` | ❌ | Browser scale factor. Pass a number between 0.1 to 3. Defaults to 1. (Default: `1`) |
| `theme` | `Theme` | ❌ | Browser theme. Pass &quot;light&quot; or &quot;dark&quot;. Defaults to &quot;light&quot;. (Default: `light`)<br>**Allowed:** `light`, `dark` |
| `userAgent` | `string` | ❌ | Custom user agent string. Defaults to browser default. |
| `fullpage` | `boolean` | ❌ | Capture full page scroll. Pass 0 for viewport only, or 1 for full page. Defaults to 0. |
| `locale` | `string` | ❌ | Browser locale (e.g., &quot;en-US&quot;, &quot;fr-FR&quot;). Defaults to browser default. |
| `timezone` | `Timezone` | ❌ | IANA timezone identifier (e.g., &quot;America/New_York&quot;, &quot;Europe/London&quot;). Defaults to browser default.<br>**Allowed:** `africa/abidjan`, `africa/accra`, `africa/addis_ababa`, `africa/algiers`, `africa/asmara`, `africa/bamako`, `africa/bangui`, `africa/banjul`, `africa/bissau`, `africa/blantyre`, `africa/brazzaville`, `africa/bujumbura`, `africa/cairo`, `africa/casablanca`, `africa/ceuta`, `africa/conakry`, `africa/dakar`, `africa/dar_es_salaam`, `africa/djibouti`, `africa/douala`, `africa/el_aaiun`, `africa/freetown`, `africa/gaborone`, `africa/harare`, `africa/johannesburg`, `africa/juba`, `africa/kampala`, `africa/khartoum`, `africa/kigali`, `africa/kinshasa`, `africa/lagos`, `africa/libreville`, `africa/lome`, `africa/luanda`, `africa/lubumbashi`, `africa/lusaka`, `africa/malabo`, `africa/maputo`, `africa/maseru`, `africa/mbabane`, `africa/mogadishu`, `africa/monrovia`, `africa/nairobi`, `africa/ndjamena`, `africa/niamey`, `africa/nouakchott`, `africa/ouagadougou`, `africa/porto-novo`, `africa/sao_tome`, `africa/tripoli`, `africa/tunis`, `africa/windhoek`, `america/adak`, `america/anchorage`, `america/anguilla`, `america/antigua`, `america/araguaina`, `america/argentina/buenos_aires`, `america/argentina/catamarca`, `america/argentina/cordoba`, `america/argentina/jujuy`, `america/argentina/la_rioja`, `america/argentina/mendoza`, `america/argentina/rio_gallegos`, `america/argentina/salta`, `america/argentina/san_juan`, `america/argentina/san_luis`, `america/argentina/tucuman`, `america/argentina/ushuaia`, `america/aruba`, `america/asuncion`, `america/atikokan`, `america/bahia`, `america/bahia_banderas`, `america/barbados`, `america/belem`, `america/belize`, `america/blanc-sablon`, `america/boa_vista`, `america/bogota`, `america/boise`, `america/cambridge_bay`, `america/campo_grande`, `america/cancun`, `america/caracas`, `america/cayenne`, `america/cayman`, `america/chicago`, `america/chihuahua`, `america/ciudad_juarez`, `america/costa_rica`, `america/coyhaique`, `america/creston`, `america/cuiaba`, `america/curacao`, `america/danmarkshavn`, `america/dawson`, `america/dawson_creek`, `america/denver`, `america/detroit`, `america/dominica`, `america/edmonton`, `america/eirunepe`, `america/el_salvador`, `america/fort_nelson`, `america/fortaleza`, `america/glace_bay`, `america/goose_bay`, `america/grand_turk`, `america/grenada`, `america/guadeloupe`, `america/guatemala`, `america/guayaquil`, `america/guyana`, `america/halifax`, `america/havana`, `america/hermosillo`, `america/indiana/indianapolis`, `america/indiana/knox`, `america/indiana/marengo`, `america/indiana/petersburg`, `america/indiana/tell_city`, `america/indiana/vevay`, `america/indiana/vincennes`, `america/indiana/winamac`, `america/inuvik`, `america/iqaluit`, `america/jamaica`, `america/juneau`, `america/kentucky/louisville`, `america/kentucky/monticello`, `america/kralendijk`, `america/la_paz`, `america/lima`, `america/los_angeles`, `america/lower_princes`, `america/maceio`, `america/managua`, `america/manaus`, `america/marigot`, `america/martinique`, `america/matamoros`, `america/mazatlan`, `america/menominee`, `america/merida`, `america/metlakatla`, `america/mexico_city`, `america/miquelon`, `america/moncton`, `america/monterrey`, `america/montevideo`, `america/montserrat`, `america/nassau`, `america/new_york`, `america/nome`, `america/noronha`, `america/north_dakota/beulah`, `america/north_dakota/center`, `america/north_dakota/new_salem`, `america/nuuk`, `america/ojinaga`, `america/panama`, `america/paramaribo`, `america/phoenix`, `america/port-au-prince`, `america/port_of_spain`, `america/porto_velho`, `america/puerto_rico`, `america/punta_arenas`, `america/rankin_inlet`, `america/recife`, `america/regina`, `america/resolute`, `america/rio_branco`, `america/santarem`, `america/santiago`, `america/santo_domingo`, `america/sao_paulo`, `america/scoresbysund`, `america/sitka`, `america/st_barthelemy`, `america/st_johns`, `america/st_kitts`, `america/st_lucia`, `america/st_thomas`, `america/st_vincent`, `america/swift_current`, `america/tegucigalpa`, `america/thule`, `america/tijuana`, `america/toronto`, `america/tortola`, `america/vancouver`, `america/whitehorse`, `america/winnipeg`, `america/yakutat`, `antarctica/casey`, `antarctica/davis`, `antarctica/dumontdurville`, `antarctica/macquarie`, `antarctica/mawson`, `antarctica/mcmurdo`, `antarctica/palmer`, `antarctica/rothera`, `antarctica/syowa`, `antarctica/troll`, `antarctica/vostok`, `arctic/longyearbyen`, `asia/aden`, `asia/almaty`, `asia/amman`, `asia/anadyr`, `asia/aqtau`, `asia/aqtobe`, `asia/ashgabat`, `asia/atyrau`, `asia/baghdad`, `asia/bahrain`, `asia/baku`, `asia/bangkok`, `asia/barnaul`, `asia/beirut`, `asia/bishkek`, `asia/brunei`, `asia/chita`, `asia/colombo`, `asia/damascus`, `asia/dhaka`, `asia/dili`, `asia/dubai`, `asia/dushanbe`, `asia/famagusta`, `asia/gaza`, `asia/hebron`, `asia/ho_chi_minh`, `asia/hong_kong`, `asia/hovd`, `asia/irkutsk`, `asia/jakarta`, `asia/jayapura`, `asia/jerusalem`, `asia/kabul`, `asia/kamchatka`, `asia/karachi`, `asia/kathmandu`, `asia/khandyga`, `asia/kolkata`, `asia/krasnoyarsk`, `asia/kuala_lumpur`, `asia/kuching`, `asia/kuwait`, `asia/macau`, `asia/magadan`, `asia/makassar`, `asia/manila`, `asia/muscat`, `asia/nicosia`, `asia/novokuznetsk`, `asia/novosibirsk`, `asia/omsk`, `asia/oral`, `asia/phnom_penh`, `asia/pontianak`, `asia/pyongyang`, `asia/qatar`, `asia/qostanay`, `asia/qyzylorda`, `asia/riyadh`, `asia/sakhalin`, `asia/samarkand`, `asia/seoul`, `asia/shanghai`, `asia/singapore`, `asia/srednekolymsk`, `asia/taipei`, `asia/tashkent`, `asia/tbilisi`, `asia/tehran`, `asia/thimphu`, `asia/tokyo`, `asia/tomsk`, `asia/ulaanbaatar`, `asia/urumqi`, `asia/ust-nera`, `asia/vientiane`, `asia/vladivostok`, `asia/yakutsk`, `asia/yangon`, `asia/yekaterinburg`, `asia/yerevan`, `atlantic/azores`, `atlantic/bermuda`, `atlantic/canary`, `atlantic/cape_verde`, `atlantic/faroe`, `atlantic/madeira`, `atlantic/reykjavik`, `atlantic/south_georgia`, `atlantic/st_helena`, `atlantic/stanley`, `australia/adelaide`, `australia/brisbane`, `australia/broken_hill`, `australia/darwin`, `australia/eucla`, `australia/hobart`, `australia/lindeman`, `australia/lord_howe`, `australia/melbourne`, `australia/perth`, `australia/sydney`, `europe/amsterdam`, `europe/andorra`, `europe/astrakhan`, `europe/athens`, `europe/belgrade`, `europe/berlin`, `europe/bratislava`, `europe/brussels`, `europe/bucharest`, `europe/budapest`, `europe/busingen`, `europe/chisinau`, `europe/copenhagen`, `europe/dublin`, `europe/gibraltar`, `europe/guernsey`, `europe/helsinki`, `europe/isle_of_man`, `europe/istanbul`, `europe/jersey`, `europe/kaliningrad`, `europe/kirov`, `europe/kyiv`, `europe/lisbon`, `europe/ljubljana`, `europe/london`, `europe/luxembourg`, `europe/madrid`, `europe/malta`, `europe/mariehamn`, `europe/minsk`, `europe/monaco`, `europe/moscow`, `europe/oslo`, `europe/paris`, `europe/podgorica`, `europe/prague`, `europe/riga`, `europe/rome`, `europe/samara`, `europe/san_marino`, `europe/sarajevo`, `europe/saratov`, `europe/simferopol`, `europe/skopje`, `europe/sofia`, `europe/stockholm`, `europe/tallinn`, `europe/tirane`, `europe/ulyanovsk`, `europe/vaduz`, `europe/vatican`, `europe/vienna`, `europe/vilnius`, `europe/volgograd`, `europe/warsaw`, `europe/zagreb`, `europe/zurich`, `indian/antananarivo`, `indian/chagos`, `indian/christmas`, `indian/cocos`, `indian/comoro`, `indian/kerguelen`, `indian/mahe`, `indian/maldives`, `indian/mauritius`, `indian/mayotte`, `indian/reunion`, `pacific/apia`, `pacific/auckland`, `pacific/bougainville`, `pacific/chatham`, `pacific/chuuk`, `pacific/easter`, `pacific/efate`, `pacific/fakaofo`, `pacific/fiji`, `pacific/funafuti`, `pacific/galapagos`, `pacific/gambier`, `pacific/guadalcanal`, `pacific/guam`, `pacific/honolulu`, `pacific/kanton`, `pacific/kiritimati`, `pacific/kosrae`, `pacific/kwajalein`, `pacific/majuro`, `pacific/marquesas`, `pacific/midway`, `pacific/nauru`, `pacific/niue`, `pacific/norfolk`, `pacific/noumea`, `pacific/pago_pago`, `pacific/palau`, `pacific/pitcairn`, `pacific/pohnpei`, `pacific/port_moresby`, `pacific/rarotonga`, `pacific/saipan`, `pacific/tahiti`, `pacific/tarawa`, `pacific/tongatapu`, `pacific/wake`, `pacific/wallis`, `utc` |
| `latitude` | `number` | ❌ | Geolocation latitude. Pass a number between -90 to 90. Defaults to 0. |
| `longitude` | `number` | ❌ | Geolocation longitude. Pass a number between -180 to 180. Defaults to 0. |
| `accuracy` | `number` | ❌ | Geolocation accuracy in meters. Pass a number between 0 to 100000. Defaults to 0. |
| `touch` | `boolean` | ❌ | Enable touch support. Pass 0 for no touch, or 1 for touch enabled. Defaults to 0. |
| `permissions` | `BrowserPermission` | ❌ | Browser permissions to grant. Pass an array of permission names like [&quot;geolocation&quot;, &quot;camera&quot;, &quot;microphone&quot;]. Defaults to empty. (Default: `[]`)<br>**Allowed:** `geolocation`, `camera`, `microphone`, `notifications`, `midi`, `push`, `clipboard-read`, `clipboard-write`, `payment-handler`, `usb`, `bluetooth`, `accelerometer`, `gyroscope`, `magnetometer`, `ambient-light-sensor`, `background-sync`, `persistent-storage`, `screen-wake-lock`, `web-share`, `xr-spatial-tracking` |
| `sleep` | `number` | ❌ | Wait time in seconds before taking the screenshot. Pass an integer between 0 to 10. Defaults to 0. |
| `width` | `number` | ❌ | Output image width. Pass 0 to use original width, or an integer between 1 to 2000. Defaults to 0 (original width). |
| `height` | `number` | ❌ | Output image height. Pass 0 to use original height, or an integer between 1 to 2000. Defaults to 0 (original height). |
| `quality` | `number` | ❌ | Screenshot quality. Pass an integer between 0 to 100. Defaults to keep existing image quality. (Default: `-1`) |
| `output` | `ImageFormat` | ❌ | Output format type (jpeg, jpg, png, gif and webp).<br>**Allowed:** `jpg`, `jpeg`, `png`, `webp`, `heic`, `avif`, `gif` |

## Usage

```typescript
import { Client, Avatars, Theme, Timezone, BrowserPermission, ImageFormat } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const avatars = new Avatars(client);
const result = avatars.getScreenshot({
  url: 'https://example.com',
  headers: {
    "Authorization": "Bearer token123",
    "X-Custom-Header": "value"
},
  viewportWidth: 1920,
  viewportHeight: 1080,
  scale: 2,
  theme: Theme.Light,
  userAgent: 'Mozilla/5.0 (iPhone; CPU iPhone OS 14_0 like Mac OS X) AppleWebKit/605.1.15',
  fullpage: true,
  locale: 'en-US',
  timezone: Timezone.AfricaAbidjan,
  latitude: 37.7749,
  longitude: -122.4194,
  accuracy: 100,
  touch: true,
  permissions: BrowserPermission.Geolocation,
  sleep: 3,
  width: 800,
  height: 600,
  quality: 85,
  output: ImageFormat.Jpg,
});
```
