# vps-initial

## _TODO_
<<<<<<< HEAD
add pathogen installation
add dotbot installation
=======
add pathogen installation
add dotbot installation
>>>>>>> c65d8834a915333073d5167a6eb1251f6f610fec

### System update
```
# as root
pacman -Syu
```

### Adding and enabling new user.

```
# as root
adduser -m -G wheel <username>
visudo <uncomment wheel line>
pacman -S bash-completion
```

### Enabling ufw firewall and opening SSH Limited port

```
# as root
pacman -S ufw
ufw allow SSH
ufw limit SSH
```

### Docker and docker compose install / service start / adding user to docker group
```
# as root
pacman -S docker docker-compose
systemctl enable docker
usermod -aG docker <username>
```

### Disable root account
```
$ as a regular user
sudo passwd -l root
```

- ### Various utilities install
- ```
- # as a regular user
- sudo pacman -S htop 
