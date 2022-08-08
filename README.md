# ubuntu

## Pre-requisites
```
sudo apt update
sudo apt install xorg build-essential suckless-tools libxft-dev libxinerama-dev libx11-dev
sudo apt install feh

mkdir -p ~/Public/gitrepo
cd ~/Public/gitrepo
```

## Install dwm
```
git clone https://git.suckless.org/dwm
cd dwm
sudo make clean install
```

# Install slstatus
```
git clone https://git.suckless.org/slstatus
cd slstatus
make clean install
```

## Install st
```
cd ~/Public/gitrepo
git clone https://git.suckless.org/st
cd st
sudo make clean install
```
