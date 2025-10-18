# MCP Configuration Examples

This directory contains example configuration files for setting up Model Context Protocol (MCP) servers with OpenHands CLI.

## Figma MCP Server Configurations

### Quick Setup

1. Choose the appropriate configuration file:
   - `figma-local.json` - For local Figma desktop app server (recommended)
   - `figma-remote.json` - For remote Figma hosted server
   - `figma-both.json` - For both local and remote servers (advanced)

2. Copy your chosen file to `~/.openhands/mcp.json`:
   ```bash
   cp figma-local.json ~/.openhands/mcp.json
   ```

3. Follow the prerequisites below

4. Restart OpenHands CLI to apply changes

### Configuration Files

#### `figma-local.json`
- **Best for**: Development and reliable connections
- **Requires**: Figma desktop app running
- **URL**: `http://127.0.0.1:3845/mcp`
- **Authentication**: None required

#### `figma-remote.json`
- **Best for**: Cloud-based workflows, no desktop app
- **Requires**: Figma Pro/Org/Enterprise plan
- **URL**: `https://mcp.figma.com/mcp`
- **Authentication**: OAuth (handled automatically)

#### `figma-both.json`
- **Best for**: Maximum reliability with fallback
- **Requires**: Both local and remote prerequisites
- **Provides**: Redundancy if one server is unavailable

## Usage

After configuration, use OpenHands CLI with Figma-specific prompts:

```bash
openhands
# Then in the CLI:
"Generate React code for my selected Figma frame"
"Extract design tokens from this Figma component"
"Create CSS for this Figma design: https://figma.com/file/..."
```

## Prerequisites

### For Local Server (`figma-local.json`)
1. Install Figma desktop app: https://www.figma.com/downloads/
2. Enable MCP server: Figma menu → Preferences → Enable local MCP server
3. Ensure Figma desktop app is running

### For Remote Server (`figma-remote.json`)
1. Figma account with Dev or Full seat
2. Professional, Organization, or Enterprise plan
3. OAuth authentication will be handled automatically

## Troubleshooting

- Ensure Figma desktop app is running for local server
- Verify your Figma plan supports MCP for remote server
- Check that your `~/.openhands/mcp.json` file is valid JSON
- Restart OpenHands CLI after configuration changes
- Check the [Figma MCP microagent guide](../../microagents/figma-mcp.md) for detailed troubleshooting

## Additional Resources

- [Figma MCP Server Documentation](https://developers.figma.com/docs/figma-mcp-server)
- [OpenHands MCP Documentation](https://docs.all-hands.dev/usage/mcp)
- [Model Context Protocol](https://modelcontextprotocol.io/)
