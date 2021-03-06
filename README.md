# OS X Setup Guidebook

The guidebook to configure OS X for development.

## Before setup

### Install Xcode and Command Line Tools.

```console
xcode-select --install
```

## Sublime Text

```console
SUBLIME_LOCAL_DIR="$HOME/Library/Application Support/Sublime Text 3"
SUBLIME_SYNC_DIR="$HOME/Dropbox/Sync/Sublime Text"

rm -rf "$SUBLIME_LOCAL_DIR/Installed Packages"
rm -rf "$SUBLIME_LOCAL_DIR/Packages"
ln -s "$SUBLIME_SYNC_DIR/Installed Packages" "$SUBLIME_LOCAL_DIR/Installed Packages"
ln -s "$SUBLIME_SYNC_DIR/Packages" "$SUBLIME_LOCAL_DIR/Packages"
```

## Finder

### Shell

```console
brew install zsh
sudo sh -c "cat <<EOD > /etc/paths 2>&1
/usr/local/bin
/usr/bin
/bin
/usr/local/sbin
/usr/sbin
/sbin
EOD"
sudo sh -c "echo '/usr/local/bin/zsh' >> /etc/shells"
chsh -s /usr/local/bin/zsh
```

### Homebrew

```console
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew update
brew tap homebrew/binary
brew tap homebrew/science
brew install curl --with-ssh
brew install \
	openssl \
	readline \
	git \
	wget \
	hub \
	peco \
	awscli \
	jq
```

### Ruby

```console
brew install ruby
gem update --system
gem update
gem install bundler
```

### Python

```console
brew install pyenv
pyenv install 3.4.3
pyenv global 3.4.3

pyenv install miniconda3-*
```

### OpenCV

```console
brew install opencv --with-jasper --with-qt --with-tbb
```

### Node.js

```console
brew install node
npm install -g npm-checks yo generator-license
```

### Go

```conosle
brew install go --with-cc-all
```

### ImageMagick

```console
brew cask install xquartz
brew install imagemagick
```

### TeX ###
```console
brew cask install basictex
export PATH="/Library/TeX/texbin:$PATH"
sudo tlmgr update --self --all
sudo tlmgr install collection-langjapanese draftcopy epsf boxedminipage here comment
```

### iOS Development ###
```
gem install cocoapods
```
