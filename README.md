# dotfiles
Common dotfiles for MacOS or Linux environment which I use daily for my work and personal development

> # Install Homebrew or Arkade
> ## Install Homebrew (mac)
> ```bash
> xcode-select --install
> /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
> # Turn off brew analytics
> brew analytics off
> curl -o $HOME/.Brewfile https://raw.githubusercontent.com/ozhankaraman/dotfiles/master/.Brewfile
> brew bundle install --file=$HOME/.Brewfile
> ```
> 
> ## Install Arkade (linux/arm64)
> https://github.com/alexellis/arkade
> ```bash
> curl -sLS https://get.arkade.dev | sudo sh
> arkade get argocd cilium clusterctl helm k3d k9s kind kubebuilder kubectl talosctl timoni vault
> ```

# Install Command-Line Fuzzy Finder
https://github.com/junegunn/fzf
```bash
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
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
mkdir -p $HOME/.ssh
chmod 700 $HOME/.ssh
cat << EOF >> $HOME/.ssh/config
Host *.zz.zebrastack.com
    StrictHostKeyChecking no
    UserKnownHostsFile /dev/null
EOF
chmod 600 $HOME/.ssh/config
# Download your ssh keys under .ssh folder
```

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
kubectl krew install ctx ns tree view-utilization view-allocations access-matrix who-can whoami neat get-all klock ktop node-shell oidc-login rook-ceph stern virt
```

# Last Actions

* Install Microsoft Word, Excel bundle from: www.office.com
* Download SimpleMind from: https://simpleapps.eu/download/full-edition/simplemind-pro-mac/
* Install Moom from Apple Store
* Setup Easy Move+Resize for Alt key
* Enable hot corners on top right for sleep

# Moom Setup
* MacBook 12"
  * Custom > define window size 16x16 | Move and Zoom > ⌘L => Empty one pixel around perimeter and fill 15x15
* iMac 27"
  * Custom > define window size 24x16
