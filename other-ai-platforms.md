# Using IRIS from another AI platform

Most people should simply use IRIS in Claude, where it is already switched on (see the [README](README.md)).
This page is for teams that run their own AI assistant or agent platform.

**First check:** only use AI platforms approved under the RSGx AI Use Policy. If you are unsure, ask
**ai@rsgx.com** before connecting anything.

## How IRIS connects

IRIS uses the open **Model Context Protocol (MCP)** with a standard sign-in.

| Setting | Value |
|---|---|
| Server address | `https://ai.rsgx.com/mcp/iris` |
| Transport | Streamable HTTP |
| Sign-in | OAuth 2.1. The platform finds the sign-in details itself from the server address. You sign in with your own RSGx account. |
| Client ID / secret | Not needed for Claude or for apps running on your own computer |

Every connection acts as **the person who signed in**, with that person's own AI Hub access. Nothing more.

## By platform

**Claude (claude.ai, Desktop, Cowork):** already enabled for RSGx. Nothing to set up.

**Claude Code:**
```bash
claude mcp add --transport http rsgx-iris https://ai.rsgx.com/mcp/iris
```
Then run `/mcp`, choose **rsgx-iris** and **Authenticate**.

**Other MCP apps on your own computer** (for example code editors with MCP support): add a remote MCP server with
the address above and sign in when asked. Apps that sign in through your own computer work without any extra setup.

**Hosted or company agent platforms** (anything running on a server rather than your own computer): these need a
sign-in client set up by the AI team. Email **ai@rsgx.com** with the platform name and what you want it to do.
We will never send sign-in details by chat or put them in a shared file.

## Ground rules

- Sign in as yourself. Never share your sign-in or connect IRIS under someone else's account.
- Never paste passwords, access keys or tokens into prompts, documents, code or this repository.
- If you think a key or password has been exposed, email **ai@rsgx.com** straight away. It must be changed, not
  just deleted.
- IRIS answers can include internal company information. Keep them inside RSGx systems.

## Suggested instructions for your agent

You can paste this into your agent's instructions:

> You can use the RSGx IRIS tools to work with the RSGx AI Hub. IRIS acts as the signed-in person. Use it to submit
> and track ideas, find AI Stack apps, search the RSGx intranet and answer AI Hub questions. Before submitting
> anything on the person's behalf, show them what you will submit and ask them to confirm. Never ask for or store
> passwords or keys. For Claude seat requests or changes, tell the person to email ai@rsgx.com.
