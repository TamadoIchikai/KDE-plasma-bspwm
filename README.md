# I. Introduction
- This is where i settle down after trying some linux distro, although this's just a DE combine with WE, i'm really happy with the outcome and maybe i won't change this kind of setup for a few years.
# II. Method
## 1. Dependencies
- bspwm of course
  ```bash
  sudo apt install bspwm
  ```
## 2. Firstly export PATH for kdewm
  ```bash
  vim .config/autostart/plasma-bspwm.sh
  ```
- Add into that file
  ```bash
  #!/bin/sh

  export KDEWM=/usr/bin/bspwm
  ```
## 3. Create config file and grab example from ChrisTitusTech
```bash
mkdir -p ~/.config/bspwm
mkdir -p ~/.config/sxhkd
wget -O ~/.config/bspwm/bspwmrc https://raw.githubusercontent.com/ChrisTitusTech/BSPWM-on-KDE/main/bspwmrc
wget -O ~/.config/sxhkd/sxhkdrc https://raw.githubusercontent.com/ChrisTitusTech/BSPWM-on-KDE/main/sxhkdrc
chmod +x ~/.config/bspwm/bspwmrc
chmod +x ~/.config/sxhkd/sxhkdrc
```
## 4. Mask the default kde's compositor
```bash
systemctl mask plasma-kwin_x11.service --user
```
## 5. Create .desktop file for startup
```bash
sudo wget -O /usr/share/xsessions/plasma-bspwm.desktop https://raw.githubusercontent.com/ChrisTitusTech/BSPWM-on-KDE/main/plasma-bspwm.desktop
```
