# ChatOllama
Simple Chat Interface For Ollama

### Usage
- Clone or Download the files in this repo.
- Start your Ollama Server. By default it would run locally on `http://localhost:11434`, however, you could also use a remotely hosted instance. In that case, just copy the url.
- Here's the command to launch a local server for the Chat UI
  - ```
    make chat_ollama
    ```
  - Now, the Chat UI is ready to be used. It will be hosted at
  - ```
    localhost:8000/index.html
    ```
  - Ideally, opening the `index.html` file locally in your browser should have been sufficient to use this Chat UI, however, the browser enforces CORS related security checks to prevent `file://` urls from interacting with the Ollama Service. Thus, you need to run the above command to start a local server.
  - This doesn't have any dependencies except for `python` and `make` commands which usually ship with linux and mac systems. In case that's not true, you will need to install them.
  - `[Optional]` In case you need to change the port at which the Chat UI runs, you could tweak the Makefile. You could open it in your favorite editor or run the following command
  - ```
    make edit
    ```
  - `[Optional]` And to get a list of commands, you could simply run
  - ```
    make help
    ```
