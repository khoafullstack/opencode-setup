---
description: Install MCP servers by name
agent: build
---

Install the following MCP servers by modifying the mcp field in .opencode/opencode.json:

$ARGUMENTS

Steps:
1. Read .opencode/reference/mcp-list.json to get MCP configurations
2. Read .opencode/opencode.json
3. For each MCP name in $ARGUMENTS (split by whitespace):
   - If MCP already exists in opencode.json's mcp field, skip it
   - If MCP exists in mcp-list.json, add it to opencode.json's mcp field with enabled: true
   - If MCP name not found in mcp-list.json, report error and skip
4. Write updated config back to .opencode/opencode.json with pretty formatting (2 space indent)
5. Report which MCPs were installed and which were skipped