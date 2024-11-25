# VS Code Continue extension
The VS Code Continue extension provides AI assistance and auto-complete capabilities to VS Code. I use Continue instead of Cursor.AI because with Continue, I can configure it to use locally-hosted AI. I host my local AIs with Ollama in WSL2 environment. I mostly work from my laptop with RTX 3060 and Promox Desktop with RTX 3090. 

## Installation
Install the VS Code Continue extension. If you are interested with my WSL2 setup, rough setup steps are available in this repo too.

## Config files
- config_3060.json
  - This is for the RTX 3060 8GB VRAM on my laptop.
  - Since I have limited 8gb VRAM on this laptop graphics card, I chose ```llama3.1:8b``` as coding AI Assitant and ```starcoder2:7b``` for auto-complete.  
  - Due to the limited VRAM, the laptop will have to load/unload between these two LLM, but not too bad. 
  - Remove _3060 if you want to use this file.
- config_3090.json
  - This is for the RTX 3090 24GB VRAM on my ProxMox desktop.
  - I installed a Windows 11 Pro VM into this ProxMox desktop with Ubuntu 24.04 in WSL2.
    - Unfortunately the Pro edition is needed to be able to Remote Desktop into the VM.
    - Ollama server is hosted in the WSL2 Ubuntu. 
    - I also have OpenWebUI if I want to interact with locally-hosted AI in a Web GUI interface. Easier for vision AI. 
  - Since I have 24gb VRAM on this desktop graphics card, I chose ```qwen2.5-coder``` as coding AI Assitant and ```starcoder2:7b``` for auto-complete. These two LLMs can be loaded into the 24GB VRAM with spares!
  - Remove _3090 if you want to use this file.
