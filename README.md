# ActionKit MCP Starter

## Background
This repo is an MCP server demoing ActionKit. Connect this server to your **Claude Desktop** to get access to all of ActionKit's **Slack** actions.
In this example it is assumed that your user has authed via the Paragon Connect Portal.
For the purposes of this demo we filtered actions to Slack actions, but this setting can be changed by removing the Slack filter in 
the `index.ts` file.

## Setting Up
1) First install `Claude Desktop`
2) Clone this repo and run `npm install`
3) Next run a `npm run build` to build a javascript file that will be used by Claude Desktop
4) Our last step is to point Claude Desktop to our MCP server
* Edit the Claude config file using a text editor i.e. `vi ~/Library/Application\ Support/Claude/claude_desktop_config.json`
* In the `claude_desktop_config.json` file paste this configuration:
```
{
    "mcpServers": {
      "mcp-actionkit": {
            "command": "node",
            "args": [
                "ABSOLUTE_PATH/mcp-actionkit/build/index.js"
            ],
            "env": {
                "USER": "",
                "PARAGON_PROJECT_ID": "",
                "SIGNING_KEY":""
            }
        }
    }
}
```
* Fill in your env variables with your Paragon credentials
* Note: ABSOLUTE_PATH can be found by <CMD> clicking a file in your `Finder` on Mac
5) Open Claude Desktop and there should be a `hammer icon` with the list of Slack tools
* Additionally there should also be a `plug icon` where you can verify that your app is connected to our MCP
