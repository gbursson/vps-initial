# vps-initial

## System update
```
# as root
pacman -Syu
```

## Adding and enabling new user.

```
# as root
adduser -m -G wheel <username>
visudo <uncomment wheel line>
pacman -S bash-completion
```

## Enabling ufw firewall and opening SSH Limited port

```
# as root
pacman -S ufw
ufw allow SSH
ufw limit SSH
```

## Docker and docker compose install
```
# as root
pacman -S docker docker-compose
usermod -aG docker <username>

