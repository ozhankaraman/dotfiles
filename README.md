# dotfiles
Common dotfiles for MacOS which i use daily for my work

* Install Xcode with command below:
```
xcode-select --install
```
* Install Microsoft Word, Excel bundle from: www.office.com
* Download SimpleMind from: https://simpleapps.eu/download/full-edition/simplemind-pro-mac/
* Show Status Bar: defaults write NSGlobalDomain AppleShowScrollBars -string "Always"
* Enable hot corners on top right for sleep
* Set Keyboard Shortcuts - 
  * Move focus to next window  

# Install Homebrew
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Turn off brew analytics
brew analytics off
curl -o $HOME/.Brewfile https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.Brewfile
brew bundle install --file=$HOME/.Brewfile
```

# Install oh-my-zsh and powerlevel10k plugin
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
chmod 755 /usr/local/share/zsh /usr/local/share/zsh/site-functions
rm .zshrc
wget -O $HOME/.zshrc https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.zshrc
```

# Download & Install(double click) MesloLGS fonts for iterm2 Terminal
```
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf

# iTerm2: Open iTerm2 → Preferences → Profiles → Text and set Font to MesloLGS NF. 
# Restart terminal to complete powerlevel 10k install
```

# Install .vimrc
```
wget -O $HOME/.vimrc https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.vimrc
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
  curl -fsSLO "https://github.com/kubernetes-sigs/krew/releases/latest/download/krew.tar.gz" &&
  tar zxvf krew.tar.gz &&
  KREW=./krew-"$(uname | tr '[:upper:]' '[:lower:]')_$(uname -m | sed -e 's/x86_64/amd64/' -e 's/arm.*$/arm/')" &&
  "$KREW" install krew
)

kubectl krew update
kubectl krew install ctx ns tree view-utilization view-allocations access-matrix who-can whoami neat get-all
```
