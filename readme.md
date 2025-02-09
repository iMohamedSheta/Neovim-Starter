# Neovim Starter Guide

If you are using Windows, this Neovim config includes all the packages and the Lazy package manager you need to start.

## Installation Instructions

### Windows
Place the configuration in the path `C:\Users\%USER%\AppData\Local\neovim` like `C:\Users\Mohamed Sheta\AppData\Local\neovim`.

### Linux
Place the configuration in the `.config` folder in `home/%USER%/.config/` like `\\wsl.localhost\Ubuntu\home\mohamedsheta\.config\nvim`.

### Installation Script

```bash
#!/usr/bin/bash
apt update 

echo " Starting installing Neovim..."

# Install prerequisites
apt-get install ninja-build gettext cmake curl build-essential

# clone repo
git clone https://github.com/neovim/neovim

# build and install
cd neovim
make CMAKE_BUILD_TYPE=Release
make install

cd ~

# clone .config 
git clone https://github.com/iMohamedSheta/Neovim-Starter.git neovim_config_imohamed_sheta

# copy configs
cp -r neovim_config_imohamed_sheta/nvim/ .config/nvim/

echo "Neovim Installed successfully ✅"
