> scoop install extras/archwsl
     
user

    passwd

    echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel

    useradd -m -G wheel -s /bin/bash {username}

    passwd {username}

    sudo hostnamectl hostname {newpcname}

    C:\Users\mvrshmvllxw\scoop\apps\archwsl\current\Arch.exe config --default-user {username}

keys

    gpg --refresh-keys

    sudo pacman-key --init

    sudo pacman-key --populate archlinux

    sudo pacman -Sy archlinux-keyring

    sudo pacman -Su

pacman

    sudo nano /etc/pacman.conf

check or uncomment:

    Color
    VerbosePkgLists
    ParallelDownloads = 5

add:

    ILoveCandy

mirrors

    sudo pacman -S reflector

    sudo reflector --verbose --latest 15 --sort rate --save /etc/pacman.d/mirrorlist

    sudo pacman -Sy

    sudo pacman -Su

user dirs

    sudo pacman -S xdg-user-dirs

    xdg-user-dirs-update

git

    sudo pacman -S --needed base-devel git

paru (for aur packages)

    cd ~/Downloads

    git clone https://aur.archlinux.org/paru.git

    cd paru

    makepkg -si

chaotic aur

    sudo pacman-key --recv-key 3056513887B78AEB --keyserver keyserver.ubuntu.com

    sudo pacman-key --lsign-key 3056513887B78AEB

    sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-keyring.pkg.tar.zst'

    sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-mirrorlist.pkg.tar.zst'

    sudo pacman -Sy

fonts

    sudo pacman -S otf-font-awesome ttf-firacode-nerd ttf-cascadia-code ttf-cascadia-code-nerd ttf-jetbrains-mono-nerd ttf-nerd-fonts-symbols

fish shell

    sudo pacman -S fish

    fish

    sudo chsh -s /usr/bin/fish {username}

    echo 'set -g fish_greeting' >> ~/.config/fish/config.fish

lsd

    sudo pacman -S lsd

    echo "alias ls 'lsd'" >> ~/.config/fish/config.fish

    exec fish

starship

    sudo pacman -S starship

    curl -o ~/.config/starship.toml https://raw.githubusercontent.com/mvrshmvllxw/beauty-arch-wsl/main/starship.toml

    echo 'starship init fish | source' >> ~/.config/fish/config.fish
