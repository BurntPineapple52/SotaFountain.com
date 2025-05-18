# I'm going full linux (when doing dev in windows)

I've always used powershell and vscode when working on code in windows.  Unfortunately I'm now to the point where I actually enjoy checking out open source projects on github, and let me tell ya, those things do not like windows. I get it! 

**Enter WSL!**
Obviously real devs know all about wsl, but my dumbass is just learning about this now, and I'm a big fan. 

I've been turned off in the past by trying to figure out where to store stuff and settings up the ubuntu env and all that, but with the power of aider I'm confident I can get answers and solve my problems quickly. 

https://aider.chat/docs/install.html

curl -LsSf https://aider.chat/install.sh | sh

That worked!  I also ran 

export PATH="/home/user/.local/bin:$PATH"

to make sure that the shell terminal whatever knows wtf I'm talking about when I type in aider. 

Now for config! 

### config time
I think the config yml is pretty straight forward to use.  Dump it in your home directory and you're off to the races

https://aider.chat/docs/config/aider_conf.html

In the yml I change the main model to flash preview.  

#############
Main model:

Specify the model to use for the main chat
model: gemini/gemini-2.5-flash-preview-04-17

I specify gemini/ so that liteLLM knows to use the google ai key I have, and not vertex.  I'm using the free plan too! 

Keys get set in this section.  I use openrouter and gemini, but only free models for now. 1k requests a day via OpenRouter and 500 of the 2.5 flash thinking from Google AI Studio, or the Gemini Key.  Verrryyyy attractive and probably temporary in the grand scheme of things.  Maybe not though, maybe we'll have unlimited compute in the near future. 

#############
Set an API key for a provider (eg: --api-key provider=<key> sets PROVIDER_API_KEY=<key>)
api-key: xxx
Specify multiple values like this:
api-key:
- openrouter=sk-xxxxxxxxxxxxxxxxxxxxxxx
- gemini=AIxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
#  - yyy
#  - zzz

I also use the qwen 2.5 7b instruct model from OpenRouter for my commit and chat history summarization, mostly because aider makes one of those commit messages every single time you make a change, and I'd rather not waste expensive flash tokens when I could be using super duper fast and cheap qwen tokens.  It's all free so it's a moot point for now, but SOMEDAY if compute gets less free than it is now, it's nice to know where smaller models fit.  

###########
Specify the model to use for commit messages and chat history summarization (default depends on --model)
weak-model: openrouter/qwen/qwen-2.5-7b-instruct:free


Don't forget dark mode!

###########
Use colors suitable for a dark terminal background (default: False)
dark-mode: true


You can also turn on verbose mode and add logging so you can really dive into how the tool (aider + litellm) are interacting with the LLMs. It's pretty interesting to see the different system prompts and tools. For my case, I'll leave it off for now. 

Does it work? 

Yes!