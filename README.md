# Setup de mon nouveau Macbook Air

https://www.agnosys.com/presentation-de-lagencement-simplifie-des-fenetres-sous-macos-sequoia/

- [x] iTerm
- [x] xcode
- [x] VSCode
- [ ] Claude + liste of MCP / skills (regarder pour passer au skills v2)
- [x] Love my ZSH
- [x] RunCat
- [x] node / python / java / docker
- [x] MacOS beta
- [ ] Config mail
- [ ] clé SSH pour Github
- [ ] accès home assistant / routeur
- [ ] dévérouillage Apple Watch


```
# 1. Socle
brew install git wget curl ripgrep jq tree htop

# 2. Langages
brew install nvm pyenv pyenv-virtualenv

# 3. DevOps
brew install --cask docker
brew install kubectl helm terraform awscli gh

# 4. Git tooling
brew install git-delta lazygit

# 5. Apps GUI
brew install --cask iterm2 rectangle visual-studio-code tableplus insomnia 1password

# 6. BDD locales
brew install postgresql@16 redis
```


Dans ~/.zshrc, ajouter:
```
# nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$(brew --prefix)/opt/nvm/nvm.sh" ] && source "$(brew --prefix)/opt/nvm/nvm.sh"

# pyenv
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
