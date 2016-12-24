# macOS Sierra v. 10.12 Setup 

## Preferences

- **Keyboard > Text >** Disable "Correct spelling automatically".
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **File Sharing >** Off
- **Users & Groups > Login Items >** Spectacle, Flux

### Show Library folder

```
chflags nohidden ~/Library
```

### Show hidden files

```
defaults write com.apple.finder AppleShowAllFiles YES
```

### Show path bar

```
defaults write com.apple.finder ShowPathbar -bool true
```

### Show status bar

```
defaults write com.apple.finder ShowStatusBar -bool true
```

## Software

### Homebrew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Mac App Store

```
brew install mas
```

#### Sign in

```
mas signin email@email.com
```

### Brewfile

```
touch Brewfile
```

```
tap 'caskroom/cask'

brew 'git'
brew 'node'
brew 'npm'

cask 'brackets'
cask 'flux'
cask 'firefox'
cask 'gimp'
cask 'google-chrome'
cask 'opera'
cask 'spectacle'
cask 'sequel-pro'
cask 'utorrent'
cask 'vlc'

mas 'Numbers', id: 409203825
mas 'Pages', id: 409201541
mas 'Slack', id: 803453959
mas 'Sip', id: 507257563 
mas 'Simplenote', id: 692867256 
mas 'Todoist', id: 585829637
```

### GitHub

#### Config

```
~/.gitconfig
```


#### Generate SSH key

```
ssh-keygen -t rsa -b 4096 -C "email@email.com"
```

```
[user]
	name = First Last
	email = email@email.com
[github]
	user = username
[alias]
	a = add
	ca = commit -a
	cam = commit -am
	s = status

	pom = push origin master
	pog = push origin gh-pages
	puom = pull origin master
	puog = pull origin gh-pages
    
	cob = checkout -b
```

### SSH

#### Config

```
~./ssh/config
```

```
Host example
    HostName example.com
    User example-user
    IdentityFile key.pem
```

### Bash

#### Config

```
~/.bash_profile
```

```
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```

```
source ~/.bash_profile
```

### Node Package Manager

#### Gulp

```
npm install --global gulp-cli
```

### Ruby Version Manager

#### Download rvm

```
\curl -sSL https://get.rvm.io | bash -s stable
```

#### Install Ruby version

```
rvm install 2.3.3
```

