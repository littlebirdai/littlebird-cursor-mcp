# Littlebird for Cursor

Version: 0.1.0

Bring your meetings and work memory into Cursor through Littlebird's hosted MCP server. Search saved context, find meetings, read summaries and transcripts, save new context, and create or manage routines.

## Requirements

- A paid Littlebird account.
- A current version of Cursor with local plugin imports enabled for local testing.
- Permission to access the Littlebird content used in a request.

Cursor connects to `https://mcp.littlebird.ai/mcp`. Sign in to your own Littlebird account through the browser OAuth flow. Credentials and tokens are handled by that connection flow.

## Package

This standalone repository contains the Cursor plugin manifest, MCP connection definition, setup guide, license, and Littlebird icon. It connects to the existing hosted service. It includes no scripts, hooks, application source, or application history.

Cursor discovers the connection from the root `mcp.json`:

```json
{
  "mcpServers": {
    "littlebird": {
      "url": "https://mcp.littlebird.ai/mcp"
    }
  }
}
```

## Test locally

1. Download this repository's archive, or clone it into a separate directory:

   ```sh
   git clone https://github.com/littlebirdai/littlebird-cursor-mcp.git
   ```

2. Create `~/.cursor/plugins/local/littlebird` and copy the package files into it, including the hidden `.cursor-plugin` directory. If that location already contains a plugin, use a separate test environment rather than overwriting it.
3. Restart Cursor, or run **Developer: Reload Window** from the command palette.
4. Open **Customize** and confirm the Littlebird MCP server is present and enabled.
5. Use a Littlebird tool and complete the browser OAuth flow when prompted. Sign in with a paid Littlebird account and authorize the connection.
6. Ask: "Show me my last five meetings from Littlebird." Check that the answer reflects the returned account data. An account with no meetings can return an empty result.

On Teams and Enterprise, an administrator controls local plugin imports. A marketplace installation with the same name takes precedence over this local copy.

Saving context and creating or updating routines changes the connected Littlebird account. Request those actions explicitly when testing them.

Before marketplace submission, verify plugin discovery, OAuth sign-in, and tool execution in Cursor. Package inspection alone does not verify those runtime steps.

## License

The connector configuration and documentation are available under the [MIT license](LICENSE). The Littlebird icon and Littlebird names and trademarks are excluded from that license. This repository grants no license to Littlebird's hosted service or application source; use of the service is governed by Littlebird's applicable terms.

## Links

- [Littlebird](https://littlebird.ai)
- [Littlebird MCP documentation](https://docs.littlebird.ai/docs/mcp/)
- [Cursor plugin documentation](https://cursor.com/docs/plugins)
- [Cursor plugin reference and submission requirements](https://cursor.com/docs/reference/plugins)
- [Publishing form](https://cursor.com/marketplace/publish)

For submission questions, contact [michael@littlebird.ai](mailto:michael@littlebird.ai).
