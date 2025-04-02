<div align="center">
    <img width="250" src="logo.png"/>
</div>

**Search** is a [Nerve](https://github.com/evilsocket/nerve) agent that receives a user query and generates a markdown report of the results using the Brave Search API.

## Requirements

### MCP

The [Brave Search MCP server](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) requires [an API key](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search#getting-an-api-key) and NPX:

```bash
npm i -g npx
```

While Docker is required for [mcp/fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch).

### Nerve

Make sure Nerve is installed and updated to the latest version:

```bash
pip install --upgrade nerve-adk
```

## Search

Install this agent:

```bash
# this will download and install (or update) to ~/.nerve/agents
nerve install evilsocket/search
```

Set your [Brave Search API key](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search#getting-an-api-key) and run the agent:

```bash
# use any model supported by litellm
export NERVE_GENERATOR=openai/gpt-4o
export OPENAI_API_KEY=...

# set the brave search api key
export BRAVE_API_KEY=...

nerve run search --query 'what is the most intelligent LLM?'
```