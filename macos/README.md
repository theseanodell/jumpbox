# MacOS Jumpbox

**Currently tested on MacOS Big Sur**

This is simplified guide to help navigate documentation gathered from many sources including repositories, websites, etc. All links should be considered as attribution for the fine work of the respective authors! I thank them for their efforts and you should too.

## Key Management

### SSH Key

    `ssh-keygen -t ed25519`

#### Add Keys to the following:

- [ ] [Github](https://github.com/settings/keys)
- [ ] [Gitlab](https://gitlab.com/-/profile/keys)
- [ ] [Bitbucket](https://bitbucket.org/account/settings/ssh-keys/)

## Applications

### [Visual Studio Code](https://code.visualstudio.com)

1. Navigate to URL from above and follow instructions provided.

### [Homebrew](https://brew.sh/)

1. Navigate to URL from above and follow instructions provided.

### [iterm2](https://iterm2.com)

**I prefer iTerm2 over the standard terminal app in MacOS but it is NOT required**

iTerm2 can be installed via brew or standard package installation in MacOS

#### Brew Installation

```
brew install iterm2
```

#### [iTerm2 Shell Integration](https://iterm2.com/documentation-shell-integration.html)

Not required but recommend. Follow the instructions on the link and follow the ZSH specific instructions.

## [OhMyZSH](https://ohmyz.sh/) with [Powerlevel10k Theme](https://github.com/romkatv/powerlevel10k)

1. Navigate to URL from above and follow instructions provided.

2. Fix Folder Permissions for oh-my-zsh

Check the install prompt carefully and run any associated commands to fix folder permissions.

3. Clone Powerlevel10k into OhMyZSH Theme folder.

    `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`


4. Update OhMyZSH Theme to Powerlevel10k

    `vim  ~/.zshrc`

**Set ZSH_THEME="powerlevel10k/powerlevel10k"**

5. Restart ZSH

    `source ~/.zshrc`

6. If your command prompt does not automatically start "p10k configure" after the restart of ZSH, run the following command:

    ` p10k configure `

7. Install Meslo Nerd Font

Follow the prompt to install the recommended font. Restart iTerm2 when prompted.

8. If your command prompt does not automatically restart "p10k configure" after the restart of ZSH, run the following command:

    ` p10k configure `

### Configure ZSH and Powerlevel10k in Visual Studio Code

1. In Visual Studio Code: Open File → Preferences → Settings, enter **terminal.integrated.shell.osx** in the search box 

2. Select **Edit in settings.json** and apply the following:

```
{
    "terminal.integrated.fontFamily": "MesloLGS NF",
    "terminal.integrated.shell.osx": "zsh"
}
```
3. Save changes to **settings.json**

4. Restart Visual Studio Code