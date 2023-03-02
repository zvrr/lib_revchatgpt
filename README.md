# ChatGPT <img src="https://github.com/acheong08/ChatGPT/blob/main/logo.png?raw=true" width="7%"></img>

[![PyPi](https://img.shields.io/pypi/v/revChatGPT.svg)](https://pypi.python.org/pypi/revChatGPT)
[![Downloads](https://static.pepy.tech/badge/revchatgpt)](https://pypi.python.org/pypi/revChatGPT)

Reverse Engineered ChatGPT API by OpenAI. Extensible for chatbots etc.

> ## Support my work
> Make a pull request and fix my bad code.

<<<<<<< HEAD
Discord community: https://discord.gg/WMNtbDUjUv

# V1 Standard ChatGPT
> ## Update 2023/02/14 9:00 PM GMT+8: It is working. Use this.
=======
# Installation
`pip3 install --upgrade revChatGPT`

<details>

<summary>

# V1 Standard ChatGPT
> Uses `chat.openai.com`
> - Free
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054

</summary>

> Proxy server Rate limit: 25 requests per 10 seconds (per IP)
>
> OpenAI rate limit: 50 requests per hour on free accounts. You can get around it with multi-account cycling
>
> Plus accounts has around 150 requests per hour rate limit

## Configuration

1. Create account on [OpenAI's ChatGPT](https://chat.openai.com/)
2. Save your email and password

### Authentication method: (Choose 1)
<<<<<<< HEAD
#### Email/Password
=======
#### - Email/Password
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054
Not supported for Google/Microsoft accounts
```json
{
  "email": "email",
  "password": "your password"
}
```
<<<<<<< HEAD
#### Session token
=======
#### - Session token
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054
Comes from cookies on chat.openai.com as "__Secure-next-auth.session-token"

```json
{
  "session_token": "..."
}
```
<<<<<<< HEAD
#### Access token
=======
#### - Access token
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054
https://chat.openai.com/api/auth/session
```json
{
  "access_token": "<access_token>"
}
```

<<<<<<< HEAD
#### Optional configuration:
=======
#### - Optional configuration:
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054

```json
{
  "conversation_id": "UUID...",
  "parent_id": "UUID...",
  "proxy": "...",
  "paid": false
}
```

3. Save this as `$HOME/.config/revChatGPT/config.json`
4. If you are using Windows, you will need to create an environment variable named ```HOME``` and set it to your home profile for the script to be able to locate the config.json file.

## Usage

### Command line

`python3 -m revChatGPT.V1`

```
<<<<<<< HEAD
!help - Show this message
!reset - Forget the current conversation
!config - Show the current configuration
!rollback x - Rollback the conversation (x being the number of messages to rollback)
!exit - Exit this program
```

### Developer API

=======
        ChatGPT - A command-line interface to OpenAI's ChatGPT (https://chat.openai.com/chat)
        Repo: github.com/acheong08/ChatGPT

Type '!help' to show a full list of commands

Logging in...

You:
(Press Esc followed by Enter to finish)
```

The command line interface supports multi-line inputs and allows navigation using arrow keys. Besides, you can also edit history inputs by arrow keys when the prompt is empty. It also completes your input if it finds matched previous prompts. To finish input, press `Esc` and then `Enter` as solely `Enter` itself is used for creating new line in multi-line mode.

Set the environment variable `NO_COLOR` to `true` to disable color output.


### Developer API

>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054
#### Basic example (streamed):
```python
from revChatGPT.V1 import Chatbot

chatbot = Chatbot(config={
  "email": "<your email>",
  "password": "<your password>"
})

print("Chatbot: ")
prev_text = ""
for data in chatbot.ask(
    "Hello world",
):
    message = data["message"][len(prev_text) :]
    print(message, end="", flush=True)
    prev_text = data["message"]
print()
```

#### Basic example (single result):

```python
from revChatGPT.V1 import Chatbot

chatbot = Chatbot(config={
  "email": "<your email>",
  "password": "<your password>"
})

prompt = "how many beaches does portugal have?"
response = ""

for data in chatbot.ask(
  prompt
):
    response = data["message"]

print(response)
```
#### All API methods
Refer to the [wiki](https://github.com/acheong08/ChatGPT/wiki/V1) for advanced developer usage.

<<<<<<< HEAD

> ## V2 Fast ChatGPT API is dead (broken by OpenAI)
=======
</details>


<details>

<summary>

# V3 Official Chat API
> Recently released by OpenAI
> - Costs money

</summary>

## Command line
`python3 -m revChatGPT.V3 --api_key <api_key>`

```

    ChatGPT - Official ChatGPT API
    Repo: github.com/acheong08/ChatGPT

    Type '!help' to show a full list of commands
    Press enter twice to submit your question.

    !help - Display this message
    !rollback n - Rollback the conversation by n messages
    !exit - Quit chat
```

## Developer API

### Basic example
```python
from revChatGPT.V3 import Chatbot
chatbot = Chatbot(api_key="<api_key>")
chatbot.ask("Hello world")
```

### Streaming example
```python
from revChatGPT.V3 import Chatbot
chatbot = Chatbot(api_key="<api_key>")
for data in chatbot.ask("Hello world"):
    print(data, end="", flush=True)
```

</details>
>>>>>>> 15801eb3502caba5d19fd63e1e5f7f4fcd734054



# Awesome ChatGPT

[My list](https://github.com/stars/acheong08/lists/awesome-chatgpt)

If you have a cool project you want added to the list, open an issue.

# Disclaimers

This is not an official OpenAI product. This is a personal project and is not affiliated with OpenAI in any way. Don't sue me.

# Credits

- [virtualharby](https://twitter.com/virtualharby) - Memes for emotional support
- [All contributors](https://github.com/acheong08/ChatGPT/graphs/contributors) - Pull requests

<br>
<br>
<br>

> ### Dunno why you scrolled down so far. Here's something if you're really that bored: <a href="https://www.buymeacoffee.com/acheong08"><img src="https://img.buymeacoffee.com/button-api/?text=Waste money&emoji=💸&slug=acheong08&button_colour=000000&font_colour=ffffff&font_family=Cookie&outline_colour=ffffff&coffee_colour=FFDD00" /></a>
> (Not recommended. No benefits since I make everything open source.)
> * I mean if you do have some money to waste, why not haha
