# Dotfiles

To install:

```
git clone git@github.com:andypike/dotfiles.git
cd dotfiles
rake
```

For statusbar symbols, install the powerline fonts with:

```
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
cd ..
rm -rf fonts
```

To complete the YouCompleteMe plugin installation:

```
brew install cmake
cd ~/.vim/plugged/YouCompleteMe
./install.sh
```

To enable ctags, install Exuberant Ctags:

```
brew install ctags
```

To complete the Ack plugin installation:

```
brew install the_silver_searcher
```

Upgrade Vim to 7.4 with:

```
brew install vim
```

To keep spec runs within Vim, install tmux:

```
brew install tmux
```

Then in iTerm2: iTerm > Preferences > General and set the load preferences
folder to your dotfiles folder.


