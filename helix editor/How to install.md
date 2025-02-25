Custom helix settings

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

## Create custom theme: faz_theme.toml
---
location: ~/.config/helix/themes/

```toml
# based on
inherits = "dracula"

# transparent bg
"ui.background" = {}

# status line
"ui.statusline.normal" = { fg = "dark", bg = "white", modifiers = [] }
"ui.statusline.insert" = { fg = "dark", bg = "green", modifiers = [] }
"ui.statusline.select" = { fg = "dark", bg = "blue", modifiers = [] }
"ui.statusline.inactive" = "gray"

# cursor
"ui.cursor.primary.normal" = { fg = "dark", bg = "white" }

# menu
"ui.popup" = { fg = "white", bg = "" }

# colors
[palette]
# white = "#ffffff"
gray = "#555555"
black = "#000000"
dark = "#222222"
red = "#ff0000"

```
---

## config.toml
---
location: ~/.config/helix/

```toml
theme = "faz_theme"

[keys.normal]
# p for prettier
p = [":format", ":reload"]
# q for closing current buffer
q = ":bc"
# e for exit / close view
e = ":q"
# gd for open definition on a view (at right)
g = { d = ["vsplit", "goto_definition"] }
# Control+g for opening lazygit
# C-g = [":new", ":insert-output lazygit", ":buffer-close", ":redraw", ":reload"]

[editor]
end-of-line-diagnostics = "hint"
color-modes = true
popup-border = "all"

[editor.auto-save]
focus-lost = true
after-delay.enable = true
after-delay.timeout = 300

[editor.cursor-shape]
insert = "bar"
normal = "block"
select = "underline"

[editor.statusline]
left = ["mode", "spinner"]
center = ["file-name"]
right = ["diagnostics", "selections", "position"]
mode.normal = "NORMAL"
mode.insert = "INSERT"
mode.select = "SELECT"

[editor.file-picker]
# hidden files
hidden = false

[editor.inline-diagnostics]
cursor-line = "error"

[editor.soft-wrap]
enable = true
max-wrap = 20
max-indent-retain = 0

[editor.lsp]
auto-signature-help = false
```
---

## Install languages
---
need node already installed

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
