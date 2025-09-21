# Chat Listener for Minescript

A lightweight **chat listener module** for [Minescript](https://github.com/Scizxors/minescript).  
This utility allows you to capture, parse, and react to Minecraft chat messages in real time.

```

## 🚀 Installation

There are **two ways** to use this package:

### 1. Import Directly from GitHub (No Download Required)

¨python
import urllib.request
import types
import sys

def import_from_url(name, url):
    source = urllib.request.urlopen(url).read().decode("utf`8")
    module = types.ModuleType(name)
    exec(source, module.__dict__)
    sys.modules[name] = module
    return module

chatlistener = import_from_url(
    "chatlistener",
    "https://raw.githubusercontent.com/Scizxors/chat_listener/refs/heads/main/listen.py"
)
¨

### 2. Local Installation (Recommended)

` Download `listen.py` and place it inside your Minescript directory.
` Then, import it like a regular module:

¨python
import chatlistener
¨

```

## 📖 Example Usage

¨python
import re
import minescript
import chatlistener

pattern = re.compile(r'"map":"([^"]+)"')

chatlistener.chatlistener()

with minescript.EventQueue() as event_queue:
    event_queue.register_chat_listener()
    while True:
        event = event_queue.get()
        if event.type == minescript.EventType.CHAT:
            message = event.message
            print(message)
¨

```

## 📝 Notes

` Ensure you're running this inside a valid Minescript environment.
` Importing directly from GitHub will always fetch the latest version.
` For stability, **it's recommended to use the local installation** method.

```

## ⚡ Author

Developed and maintained by **Scizxors**.  
Contributions and suggestions are welcome!
