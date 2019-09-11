# Set up

## System

#### General
- Software update
- Download chrome, install and log in
- Download Be Focused Pro and log into Apple id
- Screenshots:
```
mkdir -p ~/screenshots/
defaults write com.apple.screencapture location ~/screenshots/ && killall SystemUIServer
```

**Dock**
- position center
- minimum size
- turn hiding on
- show on genie effect
- remove unwanted apps

**Keyboard**
- input sources British
- show keyboard in menu bar
- show keyboard viewer
- modifier keys for default keyboard (Caps -> Escape)
- modifier keys for sculpt (Caps -> Escape, Control -> Control, Option -> Command, Command -> Option)
- hide from menu bar

TODO: make `backtick` right of shift key on sculpt


#### Finder
- Default new directory to jmurphy
- Remove unwanted directories
- Set key-repeat settings:
```
defaults write -g InitialKeyRepeat -int 20
defaults write -g KeyRepeat -int 2
```


#### Terminal
**Homebrew:**
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
TODO: what does this do?
```
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
brew doctor
```

BREW install process:
```
brew update                           # Fetch latest version of homebrew and formula.
brew tap caskroom/cask                # Tap the Caskroom/Cask repository from Github using HTTPS.
brew search iterm2                     # Searches all known Casks for a partial or exact match.
brew cask info iterm2                  # Displays information about the given Cask
brew cask install iterm2               # Install the given cask.
brew cleanup                          # Remove any older versions from the cellar.
```

**Iterm:**
```
brew cask install iterm2
```

**Zsh/OhMyZsh**
```
brew install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Got the following error:
```
ncurses is keg-only, which means it was not symlinked into /usr/local,
because macOS already provides this software and installing another version in
parallel can cause all kinds of trouble.

If you need to have ncurses first in your PATH run:
  echo 'export PATH="/usr/local/opt/ncurses/bin:$PATH"' >> ~/.bash_profile

For compilers to find ncurses you may need to set:
  export LDFLAGS="-L/usr/local/opt/ncurses/lib"
  export CPPFLAGS="-I/usr/local/opt/ncurses/include"

```

Update `./zshrc` from setup file. Then:
```
brew install zsh-syntax-highlighting
git clone https://github.com/lukechilds/zsh-nvm ~/.oh-my-zsh/custom/plugins/zsh-nvm
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
source .zshrc
```
**TODO:**
ZSH theme etc



**Github:**
Generate access token:
Settings > Developer Settings > Personal Access Tokens > Generate new > Select all repo
Attempt to clone a private GitHub repo.
Enter user_name & access token for password.

Set git defaults:
```
git config --global user.name "jmurphyweb"
git config --global user.email "jmurphy.web@gmail.com"
git config --global pager.branch false
git config --global core.commentChar $
```

**Heroku:**
```
brew tap heroku/brew && brew install heroku
heroku autocomplete
```


#### Text Editor
**Atom:**
```
brew cask install atom
```
**TODO:**
Atom:
packages:
autocomplete-paths, open-in-browser, file-icons, linter, eslint
themes:
atom-material-ui, atom-material-syntax

**Atom:**
```
brew cask install visual-studio-code
```
**TODO:**
vsc plugins/settings


#### Databases
**Postgres**
```
brew install postrgresql
brew services start postgresql
```
`psql` - if that doesn't work, log in using the default database:
`psql -d template1`
`template1=# CREATE DATABASE jmurphy WITH OWNER jmurphy ENCODING 'UTF8';`
quit `\q` and login again `psql`

**Redis**
```
brew install redis
```
______________________

#### OTHER TOOLS:
```
nvm install node
brew install elixir
brew cask install slack
brew cask install sourcetree
brew cask install flux
brew cask install spectacle
```

**Spectacle:**
- _cmd+shft+j,k,i_
- Launch at login
- Run as a background application
