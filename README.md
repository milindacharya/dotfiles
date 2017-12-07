![MIT License](https://img.shields.io/github/license/milindacharya/subneter.svg)

# vimdotfiles

This repo contains a vimrc file that I use for my development work. The current collection contains vimrc file for go development with autocomplete.

## Getting Started
Current vimrc file needs vim-plug which can be downloaded and installed from [vim-plug](https://github.com/junegunn/vim-plug), it also requires vim 8.1, nodejs and gopls for autocomplete.
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
Once vim-plug is installed, you can copy `vimrc` as `.vimrc` in your home directory and do the following.
```
vim +PlugInstall 
vim +GoInstallBinaries
cp coc-settings.json ~/.vim/
```
This will install vim plugins, install go binaries necessary and copy coc-settings.json to use `gopls` language server.

## Want to do a trial run without installation?
Clone this repo locally and run 
```
vagrant up && vagrant ssh
sudo su - root
vim +PlugInstall 
vim +GoInstallBinaries
```
Create a hello-world.go in `/workdir/src` to test installation.

## License
This software is licensed under the [MIT license](LICENSE.md)

## Contribution
Feel free to fork this repo or submit a pull request. 
