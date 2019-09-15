#-*- mode: ruby -*-
# vi: set ft=ruby :
#####
#
# This vagrant file is used to test vimrc script for golang development
#
#####
$script = <<SCRIPT
sudo su - root
curl -sL https://deb.nodesource.com/setup_10.x -o nodesource_setup.sh
bash nodesource_setup.sh
sudo add-apt-repository --yes ppa:jonathonf/vim
apt-get update
apt-get install -y build-essential gcc g++ make nodejs yarn vim
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
wget https://storage.googleapis.com/golang/go1.13.linux-amd64.tar.gz
tar -xf go1.13.linux-amd64.tar.gz
mv go /usr/local
mkdir -p /workdir/src
export GOROOT=/usr/local/go
export GOPATH=/workdir
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
echo "export GOROOT=/usr/local/go" >> ~/.profile
echo "export GOPATH=/workdir" >> ~/.profile
echo "export PATH=\$GOPATH/bin:\$GOROOT/bin:\$PATH" >> ~/.profile
curl https://raw.githubusercontent.com/milindacharya/dotfiles/master/vimrc --output ~/.vimrc
sudo 
echo "*** Run the following as root to debug problems ***"
echo "vim +PlugInstall"
echo "vim +GoInstallBinaries"
SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |v|
	v.memory = 4096
    end
    config.vm.synced_folder "src", "/workdir/src"
    config.vm.provision "shell", inline: $script
end
