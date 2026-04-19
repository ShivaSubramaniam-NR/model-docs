# gpt-5-chat

> **Status:** 🔴 Retiring in -4 days
> **Retirement Date:** 2026-04-15  
> **Replacement Model:** gpt-5.3-chat  
> **Replacement Status:** ✅ Deployed (northcentralus)  

---

## Overview

See the [Azure OpenAI models documentation](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models) for details about gpt-5-chat.

---

## Capabilities

| Property | Value |
|---|---|
| Context Window | N/A tokens |
| Max Output Tokens | N/A |
| API Version Used | 2024-10-21 |

---

## Deployments in This Resource Group

| Deployment Name | Version | SKU | Region | Resource |
|---|---|---|---|---|
| gpt-5-chat | 2025-10-03 | GlobalStandard | northcentralus | mcp-foundry-project26-resource |

---

## Quick Start (Python)

Install the SDK if you haven't already:

```
pip install openai
```

```python
from openai import AzureOpenAI

client = AzureOpenAI(
    azure_endpoint="https://mcp-foundry-project26-resource.openai.azure.com/",
    api_version="2024-10-21",
    api_key="<your-api-key>"          # or use DefaultAzureCredential
)

response = client.chat.completions.create(
    model="gpt-5-chat",               # deployment name (not model name)
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user",   "content": "Hello! What can you help me with today?"}
    ]
)

print(response.choices[0].message.content)
```

---

## API Reference

### Endpoint

```
POST https://mcp-foundry-project26-resource.openai.azure.com/openai/deployments/gpt-5-chat/chat/completions?api-version=2024-10-21
```

### Request Body

```json
{
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user",   "content": "Hello!"}
  ],
  "max_tokens": 1000,
  "temperature": 0.7,
  "top_p": 0.95,
  "stream": false
}
```

### Response Body

```json
{
  "id": "chatcmpl-abc123",
  "object": "chat.completions",
  "created": 1715000000,
  "model": "gpt-5-chat",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Hello! I can help you with a wide range of tasks..."
      },
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 24,
    "completion_tokens": 48,
    "total_tokens": 72
  }
}
```

---

*Last updated: 2026-04-19 15:55 | [Azure Portal](https://portal.azure.com/#resource/subscriptions/1172b053-825e-438c-8968-4fbca25c3080/resourceGroups/rg-mcp-foundry-project26/overview) | [Microsoft Learn](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models)*
