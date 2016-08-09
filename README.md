## system setup in terminal

### install homebrew

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

if that doesn't work, check [here](http://brew.sh/)

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




## git configuration & aliases

`curl <file_path> > ~/.gitignore_global`

```
git config --global user.name "Dmitry White"
git config --global user.email "white.dmitry@gmail.com"
git config --global core.autocrlf "false"
git config --global core.excludesfile ~/.gitignore_global
git config --global apply.whitespace "nowarn"
git config --global push.default "current"
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
git config --global alias.co "checkout"
git config --global alias.ci "commit"
```