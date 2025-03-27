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
* Create/edit the Claude config file using a text editor i.e. `vi ~/Library/Application\ Support/Claude/claude_desktop_config.json`
* In the `claude_desktop_config.json` file paste this configuration:
```
{
    "mcpServers": {
      "mcp-actionkit": {
            "command": "node",
            "args": [
                "ABSOLUTE_PATH/actionkit-mcp-starter/build/index.js"
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
* For the `USER` env variable, this will correspond to the logged in user authenticated in the `Paragon Connect Portal`
    * Use [demo.useparagon.com](https://demo.useparagon.com) to quickly login as your user and **authenticate to Slack** (This is a necessary for the Slack tools to be used on your behalf) 
* Note: ABSOLUTE_PATH can be found by <CMD> clicking a file in your `Finder` on Mac
5) Open Claude Desktop and there should be a `hammer icon` with the list of Slack tools
* Additionally there should also be a `plug icon` where you can verify that your app is connected to our MCP
![image](https://github.com/user-attachments/assets/ad738e67-150c-4744-a33b-7c68f334ca19)


## Cursor Setup
1) Install `Cursor` if not installed already
2) Clone this repo and run `npm install`
3) Next run a `npm run build` to build a javascript file that will be used by Cursor
4) Our last step is to point Cursor to our MCP server
* Create/edit the Claude config file using a text editor i.e. `vi ~/.cursor/mcp.json`
* In the `mcp.json` file paste this configuration:
```
{
    "mcpServers": {
      "mcp-actionkit": {
            "command": "node",
            "args": [
                "ABSOLUTE_PATH/actionkit-mcp-starter/build/index.js"
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
* For the `USER` env variable, this will correspond to the logged in user authenticated in the `Paragon Connect Portal`
    * Use [demo.useparagon.com](https://demo.useparagon.com) to quickly login as your user and **authenticate to Slack** (This is a necessary for the Slack tools to be used on your behalf) 
* Note: ABSOLUTE_PATH can be found by <CMD> clicking a file in your `Finder` on Mac
5) Open Cursor and a Cursor Settings page should appear with available MCPs
  * You can also check by going to `Settings>Cursor Settings>MCP`
  ![image](https://github.com/user-attachments/assets/578b8bfc-c052-4a1a-9242-ac065bb01a45)

