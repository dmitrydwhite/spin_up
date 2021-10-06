## system setup in terminal

### install homebrew

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

if that doesn't work, check the correct command [here](http://brew.sh/)

if prompted to install command line tools, choose "yes"

### install git

`brew install git bash-completion`

see [here](https://github.com/bobthecow/git-flow-completion/wiki/Install-Bash-git-completion) for integrating bash completion into the bash profile

### install node

`brew install node`

### install nvm

for keeping track of all the node versions

`curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash`

if that doesn't work, troubleshoot [here](http://nvm.sh)

### install sublime

download sublimetext [here](https://www.sublimetext.com/3)

make the `subl` shortcut

`ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl`

get any custom snippets from [this repo](./Sublime_Text_Snippets/).  Put them in the Sublime Text folder: `~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`

### install vs code

download vs code [here](https://code.visualstudio.com/download)

here is a list of vs code extensions that have come in handy in the past:

* vscode-styled-components by julien poissonnier
* vs live share by microsoft
* jshint by dirk baeumer
* import cost by wix
* graphql for vscode by kumar harsh
* gitlens -- git supercharged by eric amodio
* git history by don jayamanne
* git blame by wade anderson
* eslint by dirk baeumer
* editorconfig for vscode by editorconfig
* debugger for chrome by microsoft
* css formatter by martin aeschlimann
* arduino by microsoft

see which one of these two is better for your needs:
* python for vscode by thomas haakon townsend
* pyton by microsoft

## machine setup

install [chrome](https://www.google.com/chrome/)

install [rectangle app](https://rectangleapp.com/)

install [iterm2](https://iterm2.com/downloads.html) and [powerlevel10k](https://github.com/romkatv/powerlevel10k#get-started) for cool-looking terminal

install [arduino ide and tools](https://www.arduino.cc/en/Main/Software) for funzies

## bash profile helpers

make sure that the following lines or something similar are in `~/.bash_profile`

```
export PATH="/usr/local/bin:/usr/local/sbin:$PATH"
export CLICOLOR=1
export PAGER="less"
export EDITOR="subl -w"
```

these will contribute toward having git information in the prompt

include the following line, and include the script from this repo (rename with preceding `.`):

```
source ~/.git-completion.sh
```

tinker with the following stuff to get your terminal console set up the way you like

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

```
git config --global user.email "white.dmitry@gmail.com" # Update with correct email address
git config --global user.name "Dmitry White"
git config --global core.autocrlf "false"
git config --global core.excludesfile ~/.gitignore_global
git config --global apply.whitespace "nowarn"
git config --global push.default "current"
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global alias.co "checkout"
git config --global alias.ci "commit"
```
