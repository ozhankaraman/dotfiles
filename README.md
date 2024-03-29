# dotfiles
Common dotfiles for MacOS which i use daily for my work

# Install Homebrew
```bash
xcode-select --install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Turn off brew analytics
brew analytics off
curl -o $HOME/Downloads/.Brewfile https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.Brewfile
brew bundle install --file=$HOME/Downloads/.Brewfile
```
# Install Apple Developer SF Mono Fonts: 
```
https://developer.apple.com/fonts/ 
```

# Install oh-my-zsh and powerlevel10k plugin
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
chmod 755 /usr/local/share/zsh /usr/local/share/zsh/site-functions
rm .zshrc
wget -O $HOME/.zshrc https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.zshrc
```

# Install .vimrc
```
mkdir -p $HOME/.vim/colors
wget https://github.com/morhetz/gruvbox/raw/master/colors/gruvbox.vim -O $HOME/.vim/colors/gruvbox.vim
wget -O $HOME/.vimrc https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.vimrc
```

# Configure github account access
```
curl -o $HOME/.gitconfig https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.github_username
```

# Configure .ssh/config
```bash
cat << EOF >> $HOME/.ssh/config
Host *.zz.zebrastack.com
    StrictHostKeyChecking no
    UserKnownHostsFile /dev/null
EOF
```

bugfixten

# Install Krew
https://krew.sigs.k8s.io/docs/user-guide/setup/install/
```bash
(
  set -x; cd "$(mktemp -d)" &&
  OS="$(uname | tr '[:upper:]' '[:lower:]')" &&
  ARCH="$(uname -m | sed -e 's/x86_64/amd64/' -e 's/\(arm\)\(64\)\?.*/\1\2/' -e 's/aarch64$/arm64/')" &&
  KREW="krew-${OS}_${ARCH}" &&
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/${KREW}.tar.gz" &&
  tar zxvf "${KREW}.tar.gz" &&
  ./"${KREW}" install krew
)

kubectl krew update
kubectl krew install ctx ns tree view-utilization view-allocations access-matrix who-can whoami neat get-all
```

# Last Actions

* Install Microsoft Word, Excel bundle from: www.office.com
* Download SimpleMind from: https://simpleapps.eu/download/full-edition/simplemind-pro-mac/
* Show Status Bar: defaults write NSGlobalDomain AppleShowScrollBars -string "Always"
* Install Moom from Apple Store
* Enable hot corners on top right for sleep
* Set Keyboard Shortcuts - 
  * Move focus to next window  
* Add Easy Move+Resize, Moom, Viscosity, Dropbox Programs to MacOS User Login Items for autostart up when user logons

# Moom Setup
* MacBook 12"
  * Custom > define window size 16x16 | Move and Zoom > ⌘L => Empty one pixel around perimeter and fill 15x15
* iMac 27"
  * Custom > define window size 24x16
