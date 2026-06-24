# CrossModel

**One API for every major AI model.**

CrossModel is an OpenAI- and Anthropic-compatible API gateway. Use a single API key
and one base URL to call models from OpenAI, Anthropic, DeepSeek, Google Gemini,
Alibaba Qwen, Moonshot Kimi, Zhipu GLM, and more — with unified USD billing, usage
tracking, and a public model catalog.

```bash
curl https://api.crossmodel.ai/v1/chat/completions \
  -H "Authorization: Bearer $CROSSMODEL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "deepseek/deepseek-v4-pro",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

## Why CrossModel

- **Three inbound API surfaces** — OpenAI Chat Completions (`/v1/chat/completions`),
  OpenAI Responses (`/v1/responses`), and Anthropic Messages (`/v1/messages`). Point
  your existing OpenAI or Anthropic SDK at CrossModel and keep your code unchanged.
- **Any model, any protocol** — call any model regardless of its provider's native wire
  format; CrossModel converts between protocols for you.
- **Unified billing** — one USD wallet, transparent per-request cost, no per-provider
  contracts or separate invoices.
- **Usage & cost tracking** — token counts, request volume, and spend across every model
  in one place.

## Get started

| | |
|---|---|
| 🌐 Website | https://crossmodel.ai |
| 🚀 Quickstart | https://crossmodel.ai/docs/quickstart |
| 📚 Docs | https://crossmodel.ai/docs |
| 🧩 Models & pricing | https://crossmodel.ai/models |
| 🔌 Compatibility | https://crossmodel.ai/docs/compatibility |
| ✉️ Contact | hello@crossmodel.ai |

## Compatibility

CrossModel speaks the OpenAI and Anthropic wire formats, so most existing tooling works
out of the box:

```python
from openai import OpenAI

client = OpenAI(
    api_key="<your CrossModel API key>",
    base_url="https://api.crossmodel.ai/v1",
)

resp = client.chat.completions.create(
    model="deepseek/deepseek-v4-pro",
    messages=[{"role": "user", "content": "Hello!"}],
)
print(resp.choices[0].message.content)
```

See the [docs](https://crossmodel.ai/docs) for the Anthropic SDK, streaming, tool
calling, structured output, and multimodal usage.
