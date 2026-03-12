# Setup de mon nouveau Macbook Air

Utilisation des fenêtres :
https://www.agnosys.com/presentation-de-lagencement-simplifie-des-fenetres-sous-macos-sequoia/

- [x] iTerm
- [x] xcode
- [x] VSCode
- [ ] Claude + liste of MCP / skills (regarder pour passer au skills v2)
- [x] Love my ZSH
- [x] RunCat
- [x] node / python / java / docker
- [x] MacOS beta
- [x] Config mail
- [x] clé SSH pour Github
- [x] accès home assistant / routeur
- [x] dévérouillage Apple Watch

## Installation des logiciels avec brew

```
# 1. Socle
brew install git wget curl ripgrep jq tree htop

# 2. Langages
brew install nvm pyenv pyenv-virtualenv

# 3. DevOps
brew install --cask docker
brew install kubectl helm opentofu awscli gh

# 4. Git tooling
brew install git-delta lazygit

# 5. Apps GUI
brew install --cask iterm2 visual-studio-code tableplus

# 6. BDD locales
brew install postgresql@16 redis
```


Dans ~/.zshrc, ajouter:
```
# nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$(brew --prefix)/opt/nvm/nvm.sh" ] && source "$(brew --prefix)/opt/nvm/nvm.sh"
```



## Config Claude Code — Migration nouvel ordi

### Plugins activés (enabledPlugins)

| Plugin | Source |
|---|---|
| `superpowers` | `claude-plugins-official` |
| `chrome-devtools-mcp` | `chrome-devtools-plugins` |
| `frontend-design` | `claude-plugins-official` |
| `swift-lsp` | `claude-plugins-official` |
| `figma` | `claude-plugins-official` |
| `everything-claude-code` | `everything-claude-code` |
| `ui-ux-pro-max` | `ui-ux-pro-max-skill` |

### Settings importants

| Clé | Valeur | Description |
|---|---|---|
| `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS` | `"1"` | Active le mode multi-agents (expérimental) |
| `effortLevel` | `"high"` | Niveau d'effort maximal par défaut |
| `skipDangerousModePermissionPrompt` | `true` | Pas de confirmation pour les actions en mode dangereux |

### Fichier settings.json complet

```json
{
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  },
  "enabledPlugins": {
    "superpowers@claude-plugins-official": true,
    "chrome-devtools-mcp@chrome-devtools-plugins": true,
    "frontend-design@claude-plugins-official": true,
    "swift-lsp@claude-plugins-official": true,
    "figma@claude-plugins-official": true,
    "everything-claude-code@everything-claude-code": true,
    "ui-ux-pro-max@ui-ux-pro-max-skill": true
  },
  "skipDangerousModePermissionPrompt": true,
  "effortLevel": "high"
}
```

### Transfert sur le nouvel ordi

```bash
# Créer le dossier si nécessaire
mkdir -p ~/.claude

# Copier le fichier (depuis l'ancien ordi via scp)
scp ~/.claude/settings.json user@ip-nouvel-ordi:~/.claude/settings.json

# Ou copier manuellement et coller le contenu ci-dessus dans :
nano ~/.claude/settings.json
```

### ⚠️ Points d'attention après migration

- `chrome-devtools-mcp` → source tierce, peut nécessiter une réinstallation manuelle
- `everything-claude-code` → source tierce, vérifier la disponibilité
- `ui-ux-pro-max` → source tierce, vérifier la disponibilité
- Les plugins `claude-plugins-official` devraient se résoudre automatiquement

# pyenv
```
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```


## Configuration réseau
<img width="734" height="592" alt="image" src="https://github.com/user-attachments/assets/c6589fe5-fbf2-4939-b2de-562421037268" />

IP fixes :
* 00:11:32:5E:BA:12 - 192.168.0.116
* D8:3A:DD:CA:89:1A - 192.168.0.107
* 18:41:C3:EA:FC:50 - 192.168.0.111

