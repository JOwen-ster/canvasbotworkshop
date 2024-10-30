# canvasbot

Discord Bot template for ACMCSUF-OSS Fall 2024 Discord Workshop.
- Created By Thomas Oh and Owen Sterling

Check out [Owen's Discord BOT Template](https://github.com/JOwen-ster/Discord.py-Bot-TEMPLATE) for a more complex, but complete and scalable solution, which is ideal for bot development.


## Installation / Development

### Clone this repository

- [x] HTTPS
```
git clone https://github.com/JOwen-ster/canvasbotworkshop.git
```

- [X] SSH
```
git clone git@github.com:JOwen-ster/canvasbotworkshop.git
```

- [X] GitHub CLI
```
gh repo clone JOwen-ster/canvasbotworkshop
```

Once you have the repository cloned, follow the instructions below to:
- Configure the Discord bot in the development portal
- Retrieve the Canvas API key
- Set up your local development environment (installing dependencies)

Next, on the side of your screen click on the `Installation` tab.

* Scroll down to the `Install Link` dropdown menu, make sure `Discord Provided Link` is selected.

Now, scroll down to `Default Install Settings` and click on the `SCOPES` dropdown menu under `Guild Install`.
* Under the `SCOPES` -> select `bot`.
* Under `PERMISSIONS` -> select any server permissions that your bot will need to fully function.

> [!NOTE]
> For this workshop we will use the `Administrator` permission for ease. Giving a user or bot `Administrator` will give access to all channels with all permissions regardless of how they are setup in your server.
> Bots are treated like regular membersm in a server with their access to channels and ways they interact with the server. For example able to `manage member` is not a usual default permission for most servers, it will not be for a bot unless you give it that permission.

> [!WARNING]
> Unless your Discord bot's function is for server management such as raid protection, server setup, moderation, or various non member interactive things, I would **NOT** set your permission to `Administrator` just because it is "easy". From my bot developing experience, when getting bots into bigger servers, some owners really wanna limit what it can do for security purposes. As an example, if your token gets exposed, someone logs into your bot and with a total of 20 lines of code (not joking) every server that bot is in, it will nuke, mass ping, and ban every member.

Under `Install Link`, there is a link you send to others. When clicked, that user can add your bot with all the permissions you selected to any server they have the `Manage Server` permission in (or it will not appear under the list of servers when adding).


### Before we get coding...
> [!IMPORTANT]
> Go to the `Bot` tab.
> Click `Reset Token` near the top of the page

# ***__COPY AND SAVE THIS TOKEN SOMEWHERE SECURE AND SOMEWHERE YOU CAN ACCESS IT__***

> [!CAUTION]
> # **THIS TOKEN IS HOW TO CONNECT TO YOUR APPLICATION WITH CODE, NO ONE NEEDS ANYTHING ELSE TO CONNECT/LOG INTO YOUR BOT EXCEPT THE MOST RECENT TOKEN. NEVER POST IT OR YOU RISK YOUR BOT GETTING HIGHJACKED**

> [!CAUTION]
> If you do not type `.env` in your `.gitignore` file, (the `.env` file is where you should put your token) , then GitHub bots **will** scrape your token (it has happened to me) and may use it. Discord will hopefully send you a message very fast saying they caught it and reset it since they are also scraping for Discord Bot Tokens to watch out for you and keeping your bots secure :)

![image](https://github.com/JOwen-ster/Discord_Bot_Workshop_2024/assets/111905194/79737d0c-b11f-4ee2-a0e2-f23a2d7f92f7)

## Coding the Actual Discord Bot
By the end, we will have a bot that is able to list all canvas assignments given any one of your class id's!
We will be using the [discord.py](https://discordpy.readthedocs.io/en/stable/) API wrapper in this workshop.

## **Open this repository in your favorite code editor!**

Then, create a virtual ENV by running this command when in this directory so we do not need to install dependencies onto on your remote computer.
```
python -m venv botenv
```

Then, activate the venv.

**LINX TERMINAL**
```
source botenv/bin/activate
```

**Windows Powershell**
```
botenv\Scripts\Activate.ps1
```

Then, install all requirements and dependancies from the requirements.txt located in this repo
```
pip install -r requirements.txt
```

**After you have successfully installed the libraries...**

Create a new file named `.env` (no name before the dot) and put the following in it.

> [!NOTE]
> To get a Canvas API token, login to Canvas, click `Account` -> `Settings` -> Scroll down to the bottom of the `Integrations` tab and then click `+ New Access Token`.

```sh
DISCORD_BOT_TOKEN=""
CANVAS_API_URL="https://csufullerton.instructure.com/"
CANVAS_API_TOKEN=""
```

Normally, you would create a new file named `.gitignore` and put the following inside it.
```
.env
```

I have already done this for you so all you need to do is run the bot once we add some functionality!

Refer to [main.py](/main.py) for the fully finished bot code if you are having trouble.
End of Workshop
