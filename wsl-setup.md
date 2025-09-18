# WSL setup

## Basic steps

````
wsl --install Archlinux
````

````
useradd -m -s /bin/bash stan
````

````
passwd stan
````

````
pacman -Syu
````

````
pacman -S openssh git git-delta helix gcc make libyaml
````

## Distro setup

````
wsl -d archlinux -u stan --cd /home/stan
````

````
ssh-keygen -t ed25519 -C "stanislavshandyga@gmail.com"
````

```
git clone git@github.com:stsh89/morinishi.git
```

### VS Code setup

Update `/etc/wsl.conf`

```
[user]
default=stan
```

### Git setup

```
git config --global user.email "stanislavshandyga@gmail.com"
```

```
git config --global user.name "Stanislav Shandyga"
```

```
git config --global core.editor "helix"
```

```
git config --global core.pager delta
```

```
git config --global interactive.diffFilter 'delta --color-only'
```

```
git config --global delta.navigate true
```

```
git config --global merge.conflictStyle zdiff3
```

## Project setup

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

```
curl https://mise.run | sh
```

```
echo "eval \"\$(/home/stan/.local/bin/mise activate bash)\"" >> ~/.bashrc
```

```
mise install ruby@3.4.6
```

## Common usage

````
wsl -d archlinux -u stan --cd /home/stan/morinishi
````

## Delete distribution

````
wsl --unregister archlinux
````
