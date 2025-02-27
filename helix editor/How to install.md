Custom helix settings #helix-editor #helix-install #nerd-font #helix-languages
## Nerd Font
---
1. download a font from [nerdFonts](https://www.nerdfonts.com/) (FiraCode Nerd Font)
2. unzip it
3. move it ~/.local/share/fonts/
4. reload fonts

From the downloaded folder:
```shell
unzip FiraCode.zip
mv *.ttf ~/.local/share/fonts/
fc-cache -fv
```
---

## Install helix from PPA
---
1. add PPA to repositories
2. update repositories
3. install helix

```shell
sudo add-apt-repository ppa:maveonair/helix-editor
sudo apt update
sudo apt install helix
```
---

## Install languages
---
need node already installed #nvm-install

typescript:
```shell
npm install -g typescript typescript-language-server
```

prettier:
```shell
npm install -g prettier
```

eslint:
```shell
npm install -g eslint
```
---

## languages.toml
---
location: ~/.config/helix/

```toml
[[language]]
name = "typescript"
language-servers = [ "typescript-language-server" ]
formatter = { command = "prettier", args = ["--stdin-filepath", "file.ts"] }
auto-format = false # if true, conflict with auto save
indent = { tab-width = 4, unit = "    " }

[[language]]
name = "tsx"
language-servers = [ "typescript-language-server" ]
formatter = { command = "prettier", args = ["--stdin-filepath", "file.tsx"] }
auto-format = false # if true, conflict with auto save
indent = { tab-width = 4, unit = "    " }
```
