![Microsoft Teams](https://developer.microsoft.com/en-us/graph/blogs/wp-content/uploads/2018/11/Teams-Dev-Logo-900x360.png)

osTicket-microsoft-teams
==============
An plugin for [osTicket](https://osticket.com) which posts notifications to a [Microsoft Teams](https://products.office.com/en-us/microsoft-teams/group-chat-software) channel.

Originally forked from: [https://github.com/clonemeagain/osticket-slack](https://github.com/clonemeagain/osticket-slack).

Info
------
This plugin uses CURL and was designed/tested with osTicket-1.10.1 and updated for use with osTicket-1.17.2
**Note** This has also been updated to fix the first message being repeated for each notification. It should now show new messages as they come in.

## Requirements
- php_curl
- A Office 365 account

## Install
--------
1. Clone this repo or download the zip file and place the contents into your `include/plugins` folder.
2. Now the plugin needs to be enabled & configured, so login to osTicket, select "Admin Panel" then "Manage -> Plugins" you should be seeing the list of currently installed plugins.
3. Click on `MS Teams Notifier` and paste your Teams Endpoint URL into the box (MS Teams setup instructions below). 
4. Click `Save Changes`! (If you get an error about curl, you will need to install the Curl module for PHP). 
5. After that, go back to the list of plugins and tick the checkbox next to "MS Teams Notifier" and select the "Enable" button.

## MS Teams Setup:
- Open MS Teams, navigate to channel and open COnnectors from elipsoids (...) menu
- Select Incoming Webhook and configure
- Choose webhook name and optionally change associated image
- Click Create
- Scroll down and copy the Webhook URL entirely, paste this into the `osTicket -> Admin -> Plugin -> Teams` config admin screen.

The channel you select will receive an event notice, like:
```
Ivan Pavlovic has set up a connection to Incoming Webhook so group members will be notified for this configuration with name osTicket
```


## Test!
Create a ticket!

Notes, Replies from Agents and System messages shouldn't appear, usernames are links to the user's page 
in osTicket, the Ticket subject is a link to the ticket, as is the ticket ID. 
