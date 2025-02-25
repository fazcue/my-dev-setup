location: /Downloads

```shell
LAZYGIT_VERSION=$(curl -s "https://api.github.com/repos/jesseduffield/lazygit/releases/latest" | \grep -Po '"tag_name": *"v\K[^"]*')
```

```shell
curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/download/v${LAZYGIT_VERSION}/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
```

```shell
tar xf lazygit.tar.gz lazygit
```

```shell
sudo install lazygit -D -t /usr/local/bin/
```
---

## Check version
---
```shell
lazygit --version
```
---

## config.yml
---
location: ~/.config/lazygit/

```yml
os:
  edit: 'helix {{filename}}'
  editAtLine: 'helix --line={{line}} {{filename}}'
  editAtLineAndAwait: 'helix --block --line={{line}} {{filename}}'
  editInTerminal: true
  openDirInEditor: 'helix {{dir}}'
```
