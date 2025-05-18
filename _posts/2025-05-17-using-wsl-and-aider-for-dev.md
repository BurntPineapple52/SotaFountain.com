---
layout: post
title:  "Embracing WSL and Aider for Development on Windows"
date:   2025-05-17 10:00:00 -0500
categories: wsl aider development
---

As a developer primarily working on Windows, I've often hit roadblocks when trying to work with open-source projects that assume a Linux environment. Native Windows compatibility can be a challenge!

Discovering the Windows Subsystem for Linux (WSL) has been a game-changer. It provides a seamless way to run a Linux environment directly on Windows, making it much easier to work with these projects.

To boost my productivity within this new setup, I've integrated [Aider](https://aider.chat), an AI coding assistant. Installation was straightforward using their provided script:

```bash
curl -LsSf https://aider.chat/install.sh | sh
```

Configuring Aider is done via a `~/.aider.conf.yml` file. I've set up mine to use the `gemini/gemini-2.5-flash-preview-04-17` model for main interactions and a smaller, faster model like `openrouter/qwen/qwen-2.5-7b-instruct:free` for tasks like generating commit messages. This setup, combined with API keys for OpenRouter and Gemini, provides a powerful and cost-effective AI pairing.

Other useful configurations include enabling `dark-mode` for a better terminal experience.

So far, this combination of WSL and Aider has proven to be a very effective workflow for tackling development tasks on Windows that require a Linux environment.
