## system setup in terminal

### install homebrew

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

if that doesn't work, check the correct command [here](http://brew.sh/)

### install git

`brew install git`

### install node

`brew install node`

### install sublime

download sublimetext [here](https://www.sublimetext.com/3)

make the `subl` shortcut

`ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl`

## machine setup

install [chrome](https://www.google.com/chrome/)

install [spectacle app](https://www.spectacleapp.com/)

## bash profile helpers

make sure that the following lines or something similar are in `~/.bash_profile`

```
export PATH="/usr/local/bin:/usr/local/sbin:$PATH"
export CLICOLOR=1
export PAGER="less"
export EDITOR="subl -w"
```

these will contribute toward having git information in the prompt

```
# enable git PS1 integration if possible
if [ "`type -t __git_ps1`" = 'function' ]; then
  GIT_PROMPT='$(__git_ps1 "(%s)")'
  GIT_PS1_SHOWDIRTYSTATE=true
fi

## Color Coding for Git Repos ##
BLACK="\[\033[0;30m\]"
RED="\[\033[0;31m\]"
GREEN="\[\033[0;32m\]"
BROWN="\[\033[0;33m\]"
BLUE="\[\033[0;34m\]"
PURPLE="\[\033[0;35m\]"
CYAN="\[\033[0;36m\]"
LIGHT_GRAY="\[\033[0;37m\]"
GRAY="\[\033[1;30m\]"
LIGHT_RED="\[\033[1;31m\]"
LIGHT_GREEN="\[\033[1;32m\]"
YELLOW="\[\033[1;33m\]"
LIGHT_BLUE="\[\033[1;34m\]"
LIGHT_PURPLE="\[\033[1;35m\]"
LIGHT_CYAN="\[\033[1;36m\]"
WHITE="\[\033[0;37m\]"
UNDERLINE="\[\033[4m\]"
NO_COLOUR="\[\033[0m\]"
BLUE1="\[\033[0;34m\]"
GREY1="\[\033[0;37m\]"
GREY2="\[\033[1;30m\]"
GREEN1="\[\033[0;39m\]"
RED1="\[\033[0;31m\]"
WHITE1="\[\033[1;37m\]"
END="\[\033[0m\]"

## Defines what will appear in the command prompt ##
function prompt {
  PS1="me@$BLUE1\w$GREY2$GIT_PROMPT> $END"
}

## Set the prompt ##
prompt
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
```

## git configuration & aliases

`curl https://gist.githubusercontent.com/octocat/9257657/raw/3f9569e65df83a7b328b39a091f0ce9c6efc6429/.gitignore > ~/.gitignore_global`

`git config --global user.email "white.dmitry@gmail.com" # Update with correct email address`

```
git config --global user.name "Dmitry White"
git config --global core.autocrlf "false"
git config --global core.excludesfile ~/.gitignore_global
git config --global apply.whitespace "nowarn"
git config --global push.default "current"
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global alias.co "checkout"
git config --global alias.ci "commit"
```