# createTextEmbeddings

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `texts` | `string[]` | ✅ | Array of text to generate embeddings. |
| `model` | `Model` | ❌ | The embedding model to use for generating vector embeddings. (Default: `embeddinggemma`)<br>**Allowed:** `embeddinggemma` |

## Usage

```typescript
import { Client, VectorsDB, Model, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.EmbeddingList = await vectorsDB.createTextEmbeddings({
  texts: [],
  model: Model.Embeddinggemma,
});
```

## Response Model

Returns a `Models.EmbeddingList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of embeddings that matched your query. |
| `embeddings` | `object[]` | List of embeddings. |
