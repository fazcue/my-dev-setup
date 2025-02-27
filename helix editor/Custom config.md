#helix-editor #helix-config #helix-theme
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
