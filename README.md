# Toolkami

**Seven tools is all you need**. A minimal AI agent that just works, using only seven tools. Comes with hands-free `Turbo mode` and `Hot-reloading` for self-modification.

![7 tools: Read, Write Diff, Browse, Command, Ask, Think](images/7-tools.png)

Watch it in action:
![Agent demo](images/agent-demo.gif)

**Go Turbo**: The standard pace is for chumps. Have it go full autonomous by disabling `ask`.
```python
# @mcp.tool()
async def ask(question: str) -> str:
```

## Quickstart

Devcontainer (`.devcontainer`) included and useable, otherwise proceed with manual install.

Install UV:
```bash
# OSX/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Start the MCP server:
```bash
# --reload enables Hot-reloading
cd servers && PYTHONPATH=. uv run app.py --reload

# For Browser Use (on linux)
# sudo apt-get update && sudo apt-get install -y  libglib2.0-0t64 libnss3 libnspr4 libdbus-1-3 libatk1.0-0t64 libatk-bridge2.0-0t64 libcups2t64 libxkbcommon0 libatspi2.0-0t64 libxcomposite1 libxdamage1 libxfixes3 libxrandr2 libgbm1 libpango-1.0-0 libcairo2 libasound2t64
# cd servers && uv run sync && uv run patchright install chromium
```

Start the MCP client (`self-executable UV script`):
```bash
./clients/gemini_client.py http://localhost:8081/sse # --debug
```

## Roadmap
* [ ] OpenAI compatible API, Anthropic support
* [ ] System prompt guidelines with single file project templates

## Limitations
- This is a customisable sharp tool for now. Guardrails will only be implemeted over time.