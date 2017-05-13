# Python
* Install `Python27`

```Python
yum install python27
```

* Install `pip`

> pip is a package management system used to install and manage software packages written in Python. Many packages can be found in the Python Package Index (PyPI).

```Python
curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py"
python get-pip.py
```

# Python Module `chatbot`
* Introduction

ChatterBot is a machine-learning based conversational dialog engine build in Python which makes it possible to generate responses based on collections of known conversations. The language independent design of ChatterBot allows it to be trained to speak any language.
* Install `chatbot`
```Python
pip install chatterbot
```

* Using `chatbot`
```Python
# Declare chatterbot package
from chatterbot import ChatBot
chatbot = ChatBot("Jarvis")
```

* Train a ChatBot using input string list
```Python
"""This module instantiate a ChatBot instance and train using a string list."""
from chatterbot import ChatBot
chatbot = ChatBot(
    "Jarvis",
    storage_adapter='chatterbot.storage.JsonFileStorageAdapter',
    trainer='chatterbot.trainers.ListTrainer')

conversation = [
    "What is your name",
    "My name is Jarvis"
]

chatbot.train(conversation)

response = chatbot.get_response("What is your name")
print(response)
```

* Configure the database path
```Python
chatbot.database.path = "/work/Jarvis/jarvis-kb.db"
```