# Tap
tap 'homebrew/cask'
tap 'homebrew/cask-fonts'
tap 'homebrew/cask-versions'

# Div
brew 'coreutils'
brew 'bash-completion'
brew 'git'
brew 'bash-git-prompt'
brew 'z'
brew 'gh'
brew 'cask'
brew 'zsh'
brew 'zsh-syntax-highlighting'
brew 'maven'
brew 'maven-completion'
brew 'cheat'
brew 'vim'
brew 'wget'
brew 'helm'
brew 'python'
brew 'brew-pip'
brew 'node'
brew 'npm'
brew 'exa'
brew 'kubeseal'
brew 'thefuck'
brew 'fish'
brew 'starship'
brew 'kubernetes-cli'
brew 'mkdocs'
brew 'kotlin'
brew 'postgresql@15'
brew 'asdf'

# Casks
cask 'docker'
cask 'slack'
cask 'google-chrome'
cask 'iterm2'
cask 'keystore-explorer'
cask 'visual-studio-code'
cask 'postman'
cask 'microsoft-teams'

# Temurin Java
cask 'temurin'
cask 'temurin17'
cask 'temurin8'
cask 'temurin11'




val newItems =
    nonExistingPhysicalIds
        .mapNotNull { physicalId ->
          customerAccount.getEntryForPhysicalId(physicalId)?.let { configEntry ->
            ReuseItem.create(
                physicalId = physicalId,
                depositValue = configEntry.depositValue,
                status =
                    Status(
                        value = ReuseItemStatus.DEPOSIT_ENABLED,
                        timestamp = event.timestamp,
                    ),
            )
          }
        }
        .also { createNewItems(newItems = it, event = event) }