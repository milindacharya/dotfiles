![MIT License](https://img.shields.io/github/license/milindacharya/subneter.svg)

# dotfile for vim 
This repo contains a vimrc file that I use for my development work. The current collection contains vimrc file for go development with autocomplete. It is tested with vim 8.1 and golang 1.13 for autocompletion using `gopls` implementation of Language Server Protocol. The current vimrc is tested on vim 8.1.1900 on MacOS 10.14.4 and Ubuntu 18.04 with golang 1.13

![Autocomplete in go](tty.gif)

### Backup existing configuration
Backup your existing vimrc file before changing or overwriting it.
```
cp ~/.vimrc ~/.vimrc.bak
```

### Install vim-plug to manage vim plugins
Current vimrc file needs vim-plug which can be downloaded and installed from [vim-plug](https://github.com/junegunn/vim-plug), it also requires vim 8.1, nodejs and gopls for autocomplete.
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

### Install vim plugins and settings file
Once vim-plug is installed, you can copy `vimrc` as `.vimrc` in your home directory and do the following.
```
vim +PlugInstall 
vim +GoInstallBinaries
cp coc-settings.json ~/.vim/
```
This will install vim plugins, install go binaries necessary and copy coc-settings.json to use `gopls` language server.


### Want to do a trial using vagrant to customize?
This vimrc is tested on ubuntu/bionic64 18.04 with vim 8.1. 

Clone this repo locally and run vagrant up 
```
git clone https://github.com/milindacharya/dotfiles.git
cd dotfiles
vagrant up && vagrant ssh
sudo su - root
vim +PlugInstall 
vim +GoInstallBinaries
cd /workdir/src/hello-world.go
```
Create a hello-world.go in `/workdir/src` to test installation.

## License
This software is licensed under the [MIT license](LICENSE.md)

## Contribution
Feel free to fork this repo or submit a pull request. 

