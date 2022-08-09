# ubuntu 22.04 /debian 11 - dwm

## Pre-requisites
```
sudo apt update
sudo apt install xorg build-essential suckless-tools libxft-dev libxinerama-dev libx11-dev
sudo apt install feh picom dunst udiskie network-manager-gnome udiskie lxappearance sxhkd xwallpaper xcompmgr -y
pip3 install pywal

sudo apt-get install xcb libxcb-xkb-dev x11-xkb-utils libx11-xcb-dev libxkbcommon-x11-dev -y
sudo apt install libxcb-res0-dev -y

mkdir -p ~/Public/gitrepo
```

### symlink all folders (trailing slash */) in dotfiles dir to home dir
```
cd ~/Public/gitrepo/ubuntu/dotfiles
stow -v -t ~ */
```

### if new folder is added then:
#### redo link (-R)
```
cd ~/Public/gitrepo/ubuntu/dotfiles
stow -v -R -t ~ */
```

### if folder was deleted then:
#### delete (-D flag then -R to relink)
```
vcd ~/Public/gitrepo/ubuntu/dotfiles
stow -v -D -t ~ */
stow -v -R -t ~ */
```

## Install dwm
```
cd ~/Public/gitrepo
git clone https://git.suckless.org/dwm
cd dwm
sudo make clean install
```

# Install slstatus
```
cd ~/Public/gitrepo
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
```
wget https://raw.githubusercontent.com/prakash2033/ubuntu/main/dwm/xsession.slstatus -O ~/.xsession
wget https://raw.githubusercontent.com/prakash2033/ubuntu/main/dwm/xprofile -O ~/.xprofile
```

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
cd $HOME
chmod 744 .xsession
```

### Configure Terminal
```
sudo update-alternatives --list x-terminal-emulator
sudo update-alternatives --install $(which x-terminal-emulator) x-terminal-emulator $(which st) 20
sudo update-alternatives --config x-terminal-emulator
```
