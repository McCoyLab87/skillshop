---
name: mcp-connection-diagnosis
description: Diagnose why an MCP client cannot connect to a server
tier: free
---

# Diagnose why an MCP client cannot connect to a server

1. Record client version, transport, endpoint and expected auth method. For stdio, confirm stdout carries only protocol output and inspect stderr separately.
2. Check initialize, capability negotiation and tool discovery in order. For HTTP, distinguish routing failures, authentication responses and session expiry using redacted metadata.
3. Return the earliest failed step, one minimal read-only probe and the smallest configuration correction.
