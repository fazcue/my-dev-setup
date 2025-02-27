Using gemini ai #aider-chat #aider-chat-install #aider-chat-config 

## Install aider with one-liner script
---
1. https://aider.chat/docs/install.html#one-liners

```bash
curl -LsSf https://aider.chat/install.sh | sh
```
---

## .aider.conf.yml
---
location: /home/facu

```yml
dark-mode: true
gitignore: false
auto-commits: false
auto-lint: true
check-update: true
read:
  - CONVENTIONS.md
model: gemini/gemini-exp-1206
```
---

## Add gemini api key to:
---
1. https://aistudio.google.com/apikey

```bash
# GEMINI API KEY for aider.chat
export GEMINI_API_KEY="PASTE_API_KEY_HERE"
```
---
