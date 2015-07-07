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

To complete the YouCompleteMe plugin installation you will need to:

```
brew install cmake
cd ~/.vim/plugged/YouCompleteMe
./install.sh
```

To enable ctags, install Exuberant Ctags:

```
brew install ctags
```

Then in iTerm2: iTerm > Preferences > General and set the load preferences
folder to your dotfiles folder.

Upgrade Vim to 7.4 with `brew install vim` then check the version with
`vim --version`. If it reports an older version than 7.4 either alter your path
or rename the system Vim: `which vim` to check the location then:
`sudo mv /usr/bin/vim /usr/bin/vim73`.
