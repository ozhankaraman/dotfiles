# dotfiles
Common dotfiles for MacOS which i use daily for my work

# Install Homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Turn off brew analytics
brew analytics off
curl -o $HOME/.Brewfile https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.Brewfile
brew bundle $HOME/.Brewfile
```

# Install iterm2 because BigSur does not have terminal

# Install oh-my-zsh and powerlevel10k plugin
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
chmod 755 /usr/local/share/zsh /usr/local/share/zsh/site-functions
mv .zshrc-ok .zshrc
```

# Install MesloLGS fonts for iterm2 Terminal
```
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf
mv com.googlecode.iterm2.plist  com.googlecode.iterm2.private.plist ~/Library/Preferences/

# iTerm2: Open iTerm2 → Preferences → Profiles → Text and set Font to MesloLGS NF. Alternatively, type p10k configure and answer Yes when asked whether to install Meslo Nerd Font.
```

# Configure .ssh/config
```
cat << EOF >> $HOME/.ssh/config
Host *.zz.zebrastack.com
    StrictHostKeyChecking no
    UserKnownHostsFile /dev/null
EOF
```

bugfixten

# Install Krew
https://krew.sigs.k8s.io/docs/user-guide/setup/install/
```
kubectl krew update
kubectl krew install ctx ns tree view-utilization view-allocations access-matrix who-can whoami neat get-all
```
