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
sudo make clean install
```

## Install st
```
cd ~/Public/gitrepo
git clone https://git.suckless.org/st
cd st
sudo make clean install
```
### .xsession file: use for configure dwm x session
`wget https://raw.githubusercontent.com/prakash2033/ubuntu/main/dwm/xsession.slstatus -O ~/.xsession`

### Configure X Session Manager
```
sudo update-alternatives --config x-session-manager
sudo update-alternatives --install $(which x-session-manager) x-session-manager $(which dwm) 20
sudo update-alternatives --list x-session-manager
sudo update-alternatives --config x-session-manager

```

### Support Display Manager
```
sudo wget https://raw.githubusercontent.com/prakash2033/ubuntu/main/dwm/dwm.desktop -O /usr/share/xsessions/dwm.desktop
sudo update-alternatives --install $(which x-window-manager) x-window-manager $(which dwm) 20
chmod 744 .xsession (only if it is necessary)
```

### Configure Terminal
```
sudo update-alternatives --list x-terminal-emulator
sudo update-alternatives --install $(which x-terminal-emulator) x-terminal-emulator $(which st) 20 
sudo update-alternatives --config x-terminal-emulator
```
