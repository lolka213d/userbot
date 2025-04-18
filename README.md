<p align="center">
  <img src="https://github.com/lolka213d/userbot/blob/main/userbot/utils/misc/src/logo.png" />
  <br>
  <b>Spribe-Userbot (beta)</b>
  <br>
  <b>Make your life in Telegram easier and more convenient with Spribe-Userbot</b>
  <br>
  <a href='https://github.com/lolka213d/userbot#%EF%B8%8F-installation'>
        Installation
  </a>
  –
  <a href='https://t.me/tgsscriptss'>
        Plugins
  </a>
  –
  <a href="https://github.com/lolka213d/userbot/releases">
        Releases
  </a>
  –
  <a href="https://github.com/lolka213d/userbot#%EF%B8%8F-example-of-creating-modules">
        Еxample of creating a module
  </a>
  <br>
  <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" />
  <br>
</p>

# ⚙️ Installation
> Linux, Termux (use f-droid version) and Windows [only wsl]

<pre><code>pkg install --yes git python p7zip && yes | pkg update && yes | pkg upgrade && git clone https://github.com/lolka213d/userbot.git && cd spribe-userbot && pip install -r requirements.txt && python -m userbot</pre></code>

> Windows

<pre><code>1. Install python 3.9 or higher
2. Run the winStart.cmd file</pre></code>

# 🛠️ Example of creating modules
<sup>To create modules, you need to know the basics of Python and the Pyrogram library.</sup>
> 1. Importing libraries
```python
from pyrogram import Client, filters
from .help import add_command_help
```
> 2. Then you need to create a function that will perform certain actions. In the example below, the decorator `@Client.on_message` is created, which calls the `exhelp` function when the userbot receives a message with the `.exhelp` command.
```python
@Client.on_message(filters.command('exhelp', prefixes='.') & filters.me)
async def exhelp(client, message):
    await message.edit_text("example help message") # Just an example
```

<sub>It is important to remember that the function name should not be repeated anywhere. If the function name already exists somewhere, the module will not be loaded. The same applies to teams. If the command already exists somewhere, the module will not be loaded (or an error occurs).</sup>

> 3. To add a module to `.help`, use the `add_command_help` function. The example below shows the code that adds the `example` module to `.help` and defines two commands: `.command` with the description `description` and `.exHelp` with the description `example help`.

```python
add_command_help(
    "example",
    [
        [".command", "description"],
        [".exHelp", "example help"],
    ]
)
```

> The whole code:
```python
from pyrogram import Client, filters
from .help import add_command_help


@Client.on_message(filters.command('exhelp', prefixes='.') & filters.me)
async def exhelp(client, message):
    await message.edit_text("example help message")


add_command_help(
    "example",
    [
        [".exHelp", "example help"],
    ]
)
```
Did something go wrong or do you need help? - tg: @devspribe | Also, if you want to publish your module to the @tgscriptss channel, write to the telegram that is above.


# 🍃 About
<p>Spribe-Userbot is a Telegram userbot (in case you didn't know, selfbot/userbot are used to automate user accounts).
So how does it work? It works in a very simple way, using the pyrogram library, a python script connects to your account (creating a new session) and catches your commands.

Using selfbot/userbot is against Telegram's Terms of Service, and you may get banned for using it if you're not careful.

The developers are not responsible for any consequences you may encounter when using Spribe-Userbot. We are also not
responsible for any damage to chat rooms caused by using this userbot.</p>
