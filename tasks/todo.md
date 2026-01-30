# Add Grep MCP Server to Autocoder

## Todo
- [x] Add GREP_MCP_TOOLS constant after CONTEXT7_TOOLS
- [x] Add `*GREP_MCP_TOOLS` to allowed_tools list
- [x] Add `*GREP_MCP_TOOLS` to permissions_list
- [x] Add grep server config to mcp_servers dict

## Review

### Summary
Added the `@247arjun/mcp-grep` npm package as an MCP server available to the coding agent. This gives the agent 5 grep-based search tools: regex search, natural language search, match counting, file listing, and advanced grep with custom arguments.

### Changes Made
**File: `client.py`** — 4 edits:
1. **Added `GREP_MCP_TOOLS` constant** (after `CONTEXT7_TOOLS`, ~line 150) — lists the 5 tool names the MCP exposes
2. **Added to `allowed_tools`** — included `*GREP_MCP_TOOLS` in the tools list so the SDK accepts them
3. **Added to `permissions_list`** — included `*GREP_MCP_TOOLS` so the security settings allow them
4. **Added `"grep"` server config** — added the npx command entry to `mcp_servers` dict

### Notes
- The grep MCP is included in **all modes** (standard and YOLO) since text search is always useful
- Tool names are based on the package documentation; may need adjustment after testing if the MCP registers different names
- No other files were modified
