---
name: figma-mcp
type: knowledge
version: 1.0.0
agent: CodeActAgent
triggers:
- figma
- mcp
- design
- ui
- figma mcp
---

# Figma MCP Server Setup Guide

This guide helps you set up Figma's Model Context Protocol (MCP) server with OpenHands CLI to bring design context directly into your development workflow.

## What is Figma MCP?

The Figma MCP server enables AI agents to:
- Generate code from selected Figma frames
- Extract design context (variables, components, layout data)
- Retrieve Make resources from Figma files
- Keep design system components consistent with Code Connect

## Prerequisites

- **Figma Account**: Dev or Full seat on Professional, Organization, or Enterprise plans
- **OpenHands CLI**: Latest version installed
- **Figma Desktop App**: Required for local server (recommended)

## Setup Options

You can connect to Figma MCP in two ways:

### Option 1: Local MCP Server (Recommended)

The local server runs through the Figma desktop app and provides the most reliable connection.

#### Step 1: Enable Local MCP Server in Figma

1. Download and install the [Figma desktop app](https://www.figma.com/downloads/)
2. Update to the latest version
3. Open any Figma design file
4. Go to **Figma menu** → **Preferences** → **Enable local MCP server**
5. You'll see a confirmation that the server is running at `http://127.0.0.1:3845/mcp`

#### Step 2: Configure OpenHands CLI

Create the MCP configuration file:

**~/.openhands/mcp.json**
```json
{
  "mcpServers": {
    "figma-local": {
      "transport": "http",
      "url": "http://127.0.0.1:3845/mcp"
    }
  }
}
```

Then restart your OpenHands session to load the new configuration.

### Option 2: Remote MCP Server

The remote server connects directly to Figma's hosted endpoint without requiring the desktop app.

#### Configure Remote Server

Create the MCP configuration file:

**~/.openhands/mcp.json**
```json
{
  "mcpServers": {
    "figma-remote": {
      "transport": "http",
      "url": "https://mcp.figma.com/mcp"
    }
  }
}
```

Then restart your OpenHands session to load the new configuration.

## Usage

Once configured, restart OpenHands CLI for changes to take effect. You can then:

### Selection-Based Workflow
1. Select a frame or layer in Figma desktop app
2. In OpenHands CLI, prompt: "Generate code for my current Figma selection"

### Link-Based Workflow
1. Copy a Figma frame or layer link
2. In OpenHands CLI, prompt: "Generate code for this Figma design: [paste link]"

## Example Prompts

- "Generate React code for my selected Figma frame"
- "Extract design tokens from this Figma component"
- "Create CSS styles matching this Figma design: https://figma.com/file/..."
- "Generate HTML/CSS for the current Figma selection"
- "What design variables are available in this Figma file?"

## Troubleshooting

### Local Server Issues
- Ensure Figma desktop app is running and MCP server is enabled
- Check that no firewall is blocking port 3845
- Restart both Figma desktop app and OpenHands CLI

### Remote Server Issues
- Verify you have the required Figma plan (Pro/Org/Enterprise)
- Ensure you have a Dev or Full seat
- Complete OAuth authentication when prompted

### General Issues
- Restart OpenHands CLI after configuration changes
- Check that the `~/.openhands/mcp.json` file is valid JSON
- Verify server URLs are accessible

## Configuration Files

### Complete Local Setup Example
**~/.openhands/mcp.json**
```json
{
  "mcpServers": {
    "figma-local": {
      "transport": "http",
      "url": "http://127.0.0.1:3845/mcp"
    }
  }
}
```

### Complete Remote Setup Example
**~/.openhands/mcp.json**
```json
{
  "mcpServers": {
    "figma-remote": {
      "transport": "http",
      "url": "https://mcp.figma.com/mcp"
    }
  }
}
```

### Both Local and Remote (Advanced)
**~/.openhands/mcp.json**
```json
{
  "mcpServers": {
    "figma-local": {
      "transport": "http",
      "url": "http://127.0.0.1:3845/mcp"
    },
    "figma-remote": {
      "transport": "http",
      "url": "https://mcp.figma.com/mcp"
    }
  }
}
```

## Beta Notice

The Figma MCP server is currently in open beta. You may experience:
- Limited functionality
- Performance issues
- Changes to the API

For the latest updates and documentation, visit:
- [Figma MCP Server Documentation](https://developers.figma.com/docs/figma-mcp-server)
- [OpenHands MCP Documentation](https://docs.all-hands.dev/usage/mcp)

## Support

If you encounter issues:
1. Check the troubleshooting section above
2. Verify your `~/.openhands/mcp.json` file is valid JSON
3. Consult the [Figma MCP documentation](https://developers.figma.com/docs/figma-mcp-server)
4. Report issues to the OpenHands community
