# chat

Description: Send a prompt to the AI assistant and receive a response. This endpoint allows you to interact with Appwrite&#039;s AI assistant by sending questions or prompts and receiving helpful responses in real-time through a server-sent events stream.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `prompt` | `string` | ✅ | Prompt. A string containing questions asked to the AI assistant. |

## Usage

```typescript
import { Client, Assistant } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const assistant = new Assistant(client);
const result = await assistant.chat({
  prompt: '<PROMPT>',
});
```
