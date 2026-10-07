# Stack Internal plugin for AI Agents

![Stack Internal logo](assets/stack-internal-logo.png)

This plugin connects AI Agents to Stack Internal knowledge through a read-only MCP server and adds a search skill. It helps AI Agents search indexed knowledge nodes, retrieve relevant results, and cite the original sources when answering questions about your organization.

This plugin follows the [Agent Plugins 1.0.0 manifest standard](https://agent-plugins.org/schemas/1.0.0/plugin.schema.json).

## Contents

- `plugin.json` declares the plugin's name and metadata.
- `mcp.json` declares the remote Stack Internal MCP server.
- `skills/search/SKILL.md` guides AI Agents' search and source-reading workflow.

## Configure and test

The URL in `mcp.json`, `https://mcp.stackinternal.com`, is the [documented default endpoint](https://support.stackinternal.com/support/solutions/articles/22000295773-mcp-server-overview). For an EU-hosted workspace, change it to `https://mcp.eu.stackinternal.com` before distributing the plugin to those users. The current server runs at the root URL; do not append `/mcp`. Users sign in through [OAuth 2.1 with PKCE](https://support.stackinternal.com/support/solutions/articles/22000296041-mcp-server-infosec-overview-and-faq); no credentials belong in this repository.

The [current server](https://support.stackinternal.com/support/solutions/articles/22000296130-mcp-server-quickstart) exposes two read-only tools, `search_nodes` and `get_node`. Search queries and retrieved content go to the configured Stack Internal MCP server, subject to that service's access controls and your organization's policies. See the [Stack Internal privacy notice](https://policies.stackoverflow.co/internal/privacy-notice/) and [terms by plan](https://policies.stackoverflow.co/internal/) for service policies.

## Ecosystem dependent differences

- OpenAI Plugin utilizes `extensions` in `plugin.json` to define the marketplace listing.
- Claude Plugin requires a `plugin.json` and `icon.png`in the `.claude-plugin` directory for marketplace listing. The `mcp.json` file must be named `.mcp.json` as well.

## License

The plugin files are distributed under the [proprietary license](LICENSE). Stack Internal service use remains subject to the applicable service agreement and policies linked above.
