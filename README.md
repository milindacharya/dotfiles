# vimdotfiles

This repo contains a vimrc file that I use for my development work. The current collection contains vimrc file for go development with autocomplete.

## Getting Started
Current vimrc file needs vim-plug which can be downloaded and installed from [vim-plug](https://github.com/junegunn/vim-plug)
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
Once vim-plug is installed, you can either start your vim using `vim -u vimrc` and install all the plugins from vim.
```
vim +PlugInstall  +GoInstallBinaries
```
You can then copy vimrc or symlink it with ~/.vimrc

## Want to do a trial run withoug installation?
Clone this repo locally and run 
```
vagrant up && vagrant ssh
sudo su - root
vim +PlugInstall +GoInstallBinaries
```
Create a hello-world.go in `/workdir/src` to test installation.

## License
This software is licensed under the [GPL v3 license](LICENSE.md)

## Contribution
Feel free to fork this repo or submit a pull request. 
