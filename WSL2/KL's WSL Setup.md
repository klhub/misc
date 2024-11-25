## Install/Setup Steps

Apology for the formatting for now, I'll fix it later once I've acustomed to using Obsidian. 

1. Install WSL 2, I'd choose Ubuntu 24.04, should be by default too. 
https://www.youtube.com/watch?v=vxTW22y8zV8&t=1120s

2. Install MiniConda for Linux inside WSL Ubuntu. I'd use the method under "Quick command line install" section
https://docs.anaconda.com/miniconda/

3. Create a Python environment. For example, here I create a Python environment named "startracker" and activate it
conda create --name startracker -y
conda activate startracker

4. Install Ollama 
https://ollama.com/download/linux

    There are many other options like LM-Studio in Windows etc. But I like Ollama in WSL the best. Most reliable I think. The only think I don't like about Ollama is how the LLM model files are managed. But that's just minor inconvenience. 

5. Install Docker 
https://docs.docker.com/desktop/install/linux/ubuntu/

6. Install WebUI. This is the command that I used.
```
sudo docker run -d --network=host -v open-webui:/app/backend/data
OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

7. Steps 4-6 basically install and host these local servers every time you start your 
```
WSL Ubuntu
http://localhost:11434/    <--- Ollama server
http://localhost:8080/     <--- OpenWebUI
```

8. Go to your Internet browser in Windows and go to : http://localhost:8080

Create an account, this is totally local, so in the email section just make up anything. Just remember the email/username/password that you made up. Login and you'll be able to play around any LLM that you downloaded. To download LLM, go to ollama.com and find out the LLM that you want to play around. Ollama.com will give you the command to download and run the LLM in the command line. I usually just want to download, so I replace the "run" with "pull" to just download the LLM. Because I run the LLM inside WebUI. 

Llama is a good model to get started. For local GPU host, I usually prefer 8B to 15B sized models. Usually about 1GB GPU RAM for 1B parameters. 

For the autocomplete capability, I've used deepseek and starcoder, both quite good. Download them from Ollama. 
https://docs.continue.dev/customize/deep-dives/autocomplete

9. In your WSL Ubuntu prompt, type "code ." to launch VS Code for your WSL environment. Find and install the "Continue" extension. You'll need to set up the LLMs to use. I'll give you my config.json for reference. 

VS Code with Continue basically the same capability of the popular CursorAI software except you have it hosted free locally.



## Notes
1. Many Youtube videos are using Mac. I don't quite like Mac, you can see that those Mac users get excited to be able to run tiny 3B models locally, pretty armature I think haha ... Windows WSL + nVidia GPU (RTX2000 or newer series) are the cheapest, best performance and more reliable way to go I think. 

2. Other related cool video
host ALL your AI locally - Network Chuck
https://www.youtube.com/watch?v=Wjrdr0NU4Sk
