# Dotfiles

To install:

```
git clone git@github.com:andypike/dotfiles.git
cd dotfiles
rake
```

If you are using iTerm2 then go to: iTerm > Preferences > Terminal > Report Terminal Type: `xterm-256color`

For nice statusbar symbols install the powerline fonts with:

```
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```

Then in iTerm2: iTerm > Preferences > Profile > Text

Set both Regular and Non-ASCII Font to 18pt Droid Sans Mono for Powerline and set the vertical height to 1.1.

Upgrade Vim to 7.4 with `brew install vim` then check the version with `vim --version`. If it reports an
older version than 7.4 either alter your path or rename the system Vim: `which vim` to check the location
then: `sudo mv /usr/bin/vim /usr/bin/vim73`
