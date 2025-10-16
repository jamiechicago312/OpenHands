# MCP Configuration Examples

This directory contains example configuration files for setting up Model Context Protocol (MCP) servers with OpenHands CLI.

## Figma MCP Server Configurations

### Quick Setup

1. Choose the appropriate configuration file:
   - `figma-local.toml` - For local Figma desktop app server (recommended)
   - `figma-remote.toml` - For remote Figma hosted server
   - `figma-both.toml` - For both local and remote servers (advanced)

2. Copy your chosen file to `~/.openhands/config.toml`:
   ```bash
   cp figma-local.toml ~/.openhands/config.toml
   ```

3. Follow the prerequisites in the configuration file comments

4. Restart OpenHands CLI to apply changes

### Configuration Files

#### `figma-local.toml`
- **Best for**: Development and reliable connections
- **Requires**: Figma desktop app running
- **URL**: `http://127.0.0.1:3845/mcp`
- **Authentication**: None required

#### `figma-remote.toml`
- **Best for**: Cloud-based workflows, no desktop app
- **Requires**: Figma Pro/Org/Enterprise plan
- **URL**: `https://mcp.figma.com/mcp`
- **Authentication**: OAuth (handled automatically)

#### `figma-both.toml`
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

## Troubleshooting

- Use `/mcp` command in OpenHands CLI to check server status
- Ensure Figma desktop app is running for local server
- Verify your Figma plan supports MCP for remote server
- Check the [Figma MCP microagent guide](../../microagents/figma-mcp.md) for detailed troubleshooting

## Additional Resources

- [Figma MCP Server Documentation](https://developers.figma.com/docs/figma-mcp-server)
- [OpenHands MCP Documentation](https://docs.all-hands.dev/usage/mcp)
- [Model Context Protocol](https://modelcontextprotocol.io/)
