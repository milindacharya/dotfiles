# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
sudo su - root
sudo add-apt-repository -y ppa:jonathonf/vim
sudo add-apt-repository -y ppa:masterminds/glide 
sudo apt-get update
sudo apt-get install   -y  vim build-essential cmake python-dev python3-dev git glide
git clone https://github.com/milindacharya/vimdotfiles.git
cp ./vimdotfiles/vimrc ~/.vimrc
wget https://storage.googleapis.com/golang/go1.9.2.linux-amd64.tar.gz
sudo tar -xvf go1.9.2.linux-amd64.tar.gz
sudo mv go /usr/local
mkdir workdir
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
export GOROOT=/usr/local/go
export GOPATH=/workdir
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
echo "export GOROOT=/usr/local/go" >> ~/.profile
echo "export GOPATH=/workdir" >> ~/.profile
echo "export PATH=\$GOPATH/bin:\$GOROOT/bin:\$PATH" >> ~/.profile
echo "Open vim and do :PlugInstall"
SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.provider "virtualbox" do |v|
	v.memory = 4096
    end
    config.vm.synced_folder "src", "/workdir/src"
    config.vm.provision "shell", inline: $script
end
