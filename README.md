# Ollama Chat Playground

<p align="center"><a href="https://shashwat-r.github.io/OllamaChatPlayground/"><img src="/favicon.png" height="128" width="128" alt="Open Preview" title="Click To Open Ollama Chat Playground"/></a><br><a href="https://shashwat-r.github.io/OllamaChatPlayground/">Click icon to launch Ollama Chat Playground</a></p>

### Introduction
Simple Local Chat Interface For Ollama.

Specify the host, and select an Ollama Model, available through a dropdown in the playground, and you're ready to chat 👍.

<img src="/previews/preview-01.png">
<sup>*Preview Image may change with new UI updates.</sup>

### Setup and Usage

#### Assumptions
- These instructions assume a Linux or MacOS based system, where `python3` and `make` commands are (usually) already available. In case they are not, do perform a standard installation. The setup is quite minimal and should be tweakable to run on Windows systems as well in case it doesn't work as is.
- This app needs access to a running ollama server locally or remotely. (There's a field to specify the host.)

Here are the methods to run this playground.

#### Method 1: (Easiest) Local Ollama Server, Default Ollama Chat Playground Server
- This is the easiest setup as it involves no downloads of any kind. It just needs your ollama server running locally.
- Enable your local Ollama Server to get access from this repo's Github Pages
  - You need to run the `ollama serve` command locally in the following manner to prevent CORS related browser errors.
  - ```
    OLLAMA_HOST=0.0.0.0:11434 OLLAMA_ORIGINS=https://shashwat-r.github.io ollama serve
    ```
- Access the Ollama Chat Playground at https://shashwat-r.github.io/OllamaChatPlayground
- Done 👍

#### Method 2: Remote Ollama Server, Default Ollama Chat Playground Server
- Instead of hosting the Ollama Server locally, you could also host it remotely using a plethora of free or paid services. One no cost example you could try is [Google Colab](colab.research.google.com), where you host the server and expose it via services like [Ngrok](ngrok.com).
- Nevertheless, wherever the notebook is hosted, you'll need to run the same command mentioned in the previous section when running the `ollama serve` command.
  - ```
    OLLAMA_HOST=0.0.0.0:11434 OLLAMA_ORIGINS=https://shashwat-r.github.io ollama serve
    ```
- Access the Ollama Chat Playground at https://shashwat-r.github.io/OllamaChatPlayground
- Done 👍

#### Method 3: (Standard) Local Ollama Server, Local Ollama Chat Playground Server
- This is the standard way to use this application. Clone this repo or download the files using the green `<> Code` button displayed on the row below the title.
- Start your local Ollama Server. You can use the standard `ollama serve` command, or use the minimal wrapper provided in this repo's Makefile by running the command:
  - ```
    make ollama_serve
    ```
  - This command automatically sets the `OLLAMA_HOST` and `OLLAMA_ORIGINS` and runs the `ollama serve` command with it, as shown in the previous methods. This enables you to experiment with the Ollama Chat Playground at https://shashwat-r.github.io/OllamaChatPlayground with your local ollama server at:
  - ```
    http://localhost:11434
    ```
- Start the local Ollama Chat Playground by running:
  - ```
    make ollama_chat_playground
    ```
  - This will automatically launch the Playground UI in your browser at:
  - ```
    http://localhost:8000
    ```
  - In case it doesn't open automatically, do open the above link manually.
- Done 👍

#### Method 4: Remote Ollama Server, Local Ollama Chat Playground Server
- In this case, you'll still need to download the files, as in the previous method.
- However, you'll just need to run the command to start the local Ollama Chat Playground.
  - ```
    make ollama_chat_playground
    ```
  - This will automatically launch the Playground UI in your browser at:
  - ```
    http://localhost:8000
    ```
  - In case it doesn't open automatically, do open the above link manually.
- You can manually enter the link of the remote ollama server in the playground, and start using it.
- Done 👍

#### Method 5: Local Ollama Server, Remote Ollama Chat Playground Server
- This is quite similar to Method 1, and you will need to find the origin of your playground. In case you don't know it, you will be able to find it by running the following command in the Inspect Element Console of your browser, at the remote ollama chat playground webpage.
  - ```
    window.location.origin
    ```
- This would provide the `<ollama_chat_playground_origin>` for your ollama server, and you could use it in the `ollama serve` command to enable it to get accessed by the remote playground
  - ```
    OLLAMA_HOST=0.0.0.0:11434 OLLAMA_ORIGINS=<ollama_chat_playground_origin> ollama serve
    ```
- Done 👍

#### Method 6: Remote Ollama Server, Remote Ollama Chat Playground Server
- This is quite similar to Method 2, and just like the previous method, you'll need to find the origin of your playground by running the following command in the Inspect Element Console of your browser, at the remote ollama chat playground webpage.
  - ```
    window.location.origin
    ```
- This would provide the `<ollama_chat_playground_origin>` for your ollama server, and you could use it in the `ollama serve` command during the setup at the remote server location to enable it to get accessed by the remote playground
  - ```
    OLLAMA_HOST=0.0.0.0:11434 OLLAMA_ORIGINS=<ollama_chat_playground_origin> ollama serve
    ```
- Done 👍

### Additional Comments
- Ideally, opening the `index.html` file locally in your browser should have been sufficient to use this playground, however, the browser enforces CORS related security checks to prevent `file://` urls from interacting with hosted urls. Thus, you need to run the above command to start a local server.
- In case you need to change the port at which the playground runs, you could tweak the `Makefile`. It's a minimal and understandable file.
- You could open it in your favorite editor or run the following command:
  - ```
    make edit
    ```
- And to get a list of commands, you could simply run either of the two commands given below.
  - ```
    make help
    ```
  - ```
    make
    ```

### Conclusion

This is a hobby project and is in no way comparable to the [Official Ollama Chatbot](https://docs.ollama.com/integrations/onyx), but it is a fun exploration into the nuances behind LLMs and ChatBots.

The UI is workable, but is a piece of work and needs updates. However it's fun to open up Developer Tools and tinker around the elements and networking calls to understand what's happening under the hood.

Hope you have fun with this too 👍
