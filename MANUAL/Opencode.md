{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "figma": {
      "type": "remote",
      "url": "https://mcp.figma.com/mcp"
    }
  },
@@@@
}

@@@@@
{
  "$schema": "https://opencode.ai/config.json",
  "disabled_providers": [],
  "provider": {
    "localllm": {
      "name": "Local LLMs",
      "npm": "@ai-sdk/openai-compatible",
      "models": {
        "gpt-oss-120b-Q8_0-00001-of-00002.gguf": {
          "name": "gpt-oss-120b-Q8_0-00001-of-00002.gguf"
        }
      },
      "options": {
        "baseURL": "http://ai.####/api/v1",
		"apiKey": "sk-d14072d1a6924500a366ff4bf4c9542f"
      }
    }
  }
}

