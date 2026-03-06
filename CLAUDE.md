# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an n8n workflow development workspace. Work here involves building, configuring, and debugging n8n workflows via the n8n MCP server.

## Key References

- **n8n MCP server**: https://github.com/czlonkowski/n8n-mcp — MCP server that connects Claude Code to n8n. Provides tools to create, update, validate, and manage workflows directly in the n8n instance.
- **n8n Skills**: https://github.com/czlonkowski/n8n-skills — Specialized Claude Code skills for n8n workflow development (node configuration, expressions, JavaScript/Python code nodes, validation, workflow patterns).

## n8n Instance

- **URL**: `https://n8n.data.qa.leboncoin.io`
- **Config**: `.mcp.json` in this workspace (credentials stored there — do not commit)

## Available Skills

Use the `Skill` tool to invoke these specialized skills:

- **`n8n-mcp-tools-expert`** — Use when searching for nodes, validating configurations, accessing templates, managing workflows, or using any n8n-mcp tool. Start here for any n8n MCP tool question.
- **`n8n-workflow-patterns`** — Use when designing workflow architecture: webhook processing, HTTP API integration, database operations, AI agent workflows, scheduled tasks.
- **`n8n-node-configuration`** — Use when configuring nodes, understanding property dependencies, determining required fields, or choosing node `get_node` detail levels.
- **`n8n-expression-syntax`** — Use when writing or debugging `{{ }}` expressions, accessing `$json`/`$node` variables, or fixing expression errors.
- **`n8n-code-javascript`** — Use when writing JavaScript in Code nodes: `$input`/`$json`/`$node` syntax, `$helpers` HTTP requests, `DateTime` usage.
- **`n8n-code-python`** — Use when writing Python in Code nodes: `_input`/`_json`/`_node` syntax and standard library constraints.
- **`n8n-validation-expert`** — Use when encountering validation errors, false positives, or operator structure issues in workflows.

## Key Principles for n8n Workflow Development

- Always validate node configurations before deploying workflows.
- Use expression syntax (`{{ }}`) for dynamic values; avoid hardcoding data that should flow between nodes.
- Prefer built-in n8n nodes over Code nodes when a native integration exists.
- Code nodes run in a sandboxed environment — only standard library modules are available in Python; `$helpers` provides HTTP access in JavaScript.
