    
    Рабочий конфиг под mcp antigravity

C:\Users\combo\.gemini\antigravity\mcp_config.json

    {

  "mcpServers": {

    "figma": {

      "source": "custom",

      "command": "npx",

      "args": [

        "-y",

        "figma-mcp"

      ],

      "env": {

        "type": "http",

        "url": "http://127.0.0.1:3845/mcp",

        "FIGMA_API_KEY": "ваш_figma_token"

      }

    }

  }

}
