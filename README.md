## VPS Initial setup instructions (Arch Linux)

### System-wide update
```
# as root
pacman -Syu
```

---

### Enable ufw firewall and opening SSH Limited port
```
pacman -S ufw
ufw allow SSH
ufw limit SSH
```

---

### Add and enable new user (_crucial, as next step is to disable root login_).
```
# as root
useradd -m -G wheel <username>
passwd <username>
visudo
```
uncomment `%wheel ALL=(ALL) ALL` line

---

### Disable root account and disable root login for SSH
```
$ as a regular user
sudo passwd -l root
```
Modify `/etc/ssh/sshd_config` file and change `PermitRootLogin` directive to `no`.
Also, you can modify `Port` directive(s) to change/add SSH listening ports.

```
sudo vim /etc/ssh/sshd_config
```

---

Set git credential cache to 60 minutes and add basic user info to git config global file
```
git config --global credential.helper 'cache --timeout=3600'
git config --global user.name "Your Name Comes Here"
git config --global user.email you@yourdomain.example.com
```

---

### Change the hostname
```
sudo hostnamectl set-hostname <new hostname>
sudo hostnamectl set-icon-name <new hostname>
```

---

### Install dotfiles repository
```
git clone https://github.com/gbursson/dotbot ~/dotfiles
rm .bashrc
cd dotfiles/
./install
```
---

### Install Git Prompt
```
git clone https://github.com/magicmonty/bash-git-prompt.git ~/.bash-git-prompt --depth=1
```

---

### Docker install and setup

```
$ as user
sudo pacman -S docker docker-compose
sudo usermod -aG docker <username>
sudo systemctl enable docker
```



