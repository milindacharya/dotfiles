# vimdotfiles

This is a vimrc files that I use for my development work. Current collection contains vimrc file for go development with autocomplete provided by [YouCompleteMe](https://github.com/Valloric/YouCompleteMe). This work is heavily inspired by [vim-go](https://github.com/fatih/vim-go)

## Getting Started
Current vimrc file needs vim-plug which can be downloaded and installed from [vim-plug](https://github.com/junegunn/vim-plug)
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
Once vim-plug is installed, you can either start your vim using `vim -u vimrc` and install all the plugins frm vim using.
```
:PlugInstall
```
You can then copy or symlink it with to your ~/.vim/.vimrc

## Future direction
[] Support debugging for go
[] vimrc for javascript and node development

## License
This software is licensed under the [GPL v3 license](LICENSE.md)

## Contribution
Feel free to fork this repo or submit pull request. 
