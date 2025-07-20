
# bashからzshに移行

https://qiita.com/shionit/items/31bfffa5057e66e46450

```bash
cat ~/.bash_profile >> ~/.zshrc
cat ~/.bashrc >> ~/.zshrc
```

* 以下調整

```bash
[.zshrc]
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(/opt/homebrew/bin/brew shellenv)"
eval "$(nodenv init -)"
eval "$(pyenv init -)"
```

## zsh-completions

```bash
brew install zsh-completions
```

```bash
[.zshrc]
export MAC_ENV_ROOT=/Users/nomuvan/work-cursor/mac-env
for f in $MAC_ENV_ROOT/*.zsh ; do
 . $f
done
```

```bash
[.init-zsh-completions.zsh]
#!/bin/zsh
echo "init-zsh-completions"
# 補完機能を有効にする
autoload -Uz compinit
compinit

# sudo の後ろでコマンド名を補完する
zstyle ':completion:*:sudo:*' command-path /usr/local/sbin /usr/local/bin \
                   /usr/sbin /usr/bin /sbin /bin /usr/X11R6/bin

fpath=(/usr/local/share/zsh-completions $fpath)
```

## zsh-autosuggestions

```bash
brew install zsh-autosuggestions
```

```bash
[.zshrc]
source /opt/homebrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh
```

## zsh-syntax-highlighting

```bash
brew install zsh-syntax-highlighting
```

```bash
[.zshrc]
source /usr/local/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

