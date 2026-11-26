# Installing the Megido MCP server

Megido is a remote MCP server. There is nothing to install, build or run: add its endpoint to the MCP client and sign in.

- Endpoint: `https://api.megido.io/mcp`
- Transport: Streamable HTTP
- Authentication: OAuth. The client opens the Megido portal in a browser, where the person signs in, creates an account or chooses **Connect without registration**.

## Steps

1. Add a remote MCP server named `megido` with the URL `https://api.megido.io/mcp` and no command. In a client configured by JSON:

   ```json
   {
     "mcpServers": {
       "megido": {
         "url": "https://api.megido.io/mcp"
       }
     }
   }
   ```

   If the client asks for a transport type, it is Streamable HTTP (`"type": "streamableHttp"` in Cline's settings, `"type": "http"` in Claude Code and VS Code).

2. Start the connection. The client opens the Megido portal in the person's browser. Ask the person to finish the sign-in there: they can sign in, create an account, or choose **Connect without registration**, which needs no email. Do not ask the person for a password or a key: the sign-in happens in their browser.

3. Check the connection by calling the tool `capabilities` with no arguments. It is free and returns the list of tools, what each one charges for and the values their filters accept. An answer means the server is installed.

## Without a browser sign-in

A client that cannot open a browser can send an API key instead. A registered person creates the key in the Megido portal under **Keys and apps**, and the client sends it in the header `Authorization: Bearer <key>` with every request. Take the key from the person; never invent one and never write it into a file that is committed.

## After the installation

- Read the server's instructions, or call `guide`, before the first research question: they say how to read each field and what each call costs.
- The index tools (`search_cohorts`, `get_cohort`, `search_projects`, `get_project_card`) work without registration within a free monthly quota. The other tools ask the person to register.
- More: https://megido.io/connect?utm_source=cline&utm_medium=referral
