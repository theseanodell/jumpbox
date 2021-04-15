
# Ubuntu Jumpbox

**Currently tested on Ubuntu 20.04 on GCP and AWS**

This is simplified guide to help navigate documentation gathered from many sources including repositories, websites, etc. All links should be considered as attribution for the fine work of the respective authors! I thank them for their efforts and you should too.

## System Configuration

### Add Password to Ubuntu User

1. Initiate Password Manager

    `sudo passwd ubuntu`


### Update OS

1. Update OS Packages

    `sudo apt update`

2. Upgrade OS Packages

    `sudo apt upgrade`
### Packages

* zip
* zsh

    `sudo apt install zip zsh`

## Key Management

### SSH Key

    `ssh-keygen -b 4096`

#### Add Keys to the following:

- [ ] [Github](https://github.com/settings/keys)
- [ ] [Gitlab](https://gitlab.com/-/profile/keys)
- [ ] [Bitbucket](https://bitbucket.org/account/settings/ssh-keys/)


### GPG Key

##### Generate GPG Key

```
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
```

#### Add Additional Email

*This is only required if you like to keep commits separate between personal and professional.*

```
gpg --edit-key “key_id”
gpg> adduid
gpg> save
```

`gpg --armor --export “key_id”`


### Enable GPG TTY in ZSH

    `vim ~/.zshrc`

Add the following:

```
# GPG TTY
export GPG_TTY=`tty`
```

#### Add Keys to the following:

- [ ] [Github](https://github.com/settings/keys)
- [ ] [Gitlab](https://gitlab.com/-/profile/gpg_keys)

## Applications

### [Homebrew](https://brew.sh/)

1. Navigate to URL from above and follow instructions provided.

### [Menlo Fonts](https://github.com/romkatv/powerlevel10k#fonts)

1. Download fonts

```
cd /tmp
wget "url of font"
```

2. Create Fonts folder

    `mkdir ~/.fonts`

3. Move files to fonts folder

    `cp *.ttf ~/.fonts`

### [OhMyZSH with Powerlevel10k Theme](https://ohmyz.sh/)

1. Navigate to URL from above and follow instructions provided.

2. Clone Powerlevel10k into OhMyZSH Theme folder.

    `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`

3. Update OhMyZSH Theme to Powerlevel10k

    `vim  ~/.zshrc`

**Set ZSH_THEME="powerlevel10k/powerlevel10k"**

4. Source Zschrc

    `source ~/.zshrc`

### [Github CLI](https://cli.github.com/)

1. Navigate to URL from above and follow instructions provided.
2. Authenticate *gh cli* with the following command:

    `gh auth login`

### [Terraform](https://www.terraform.io/downloads.html)

1. Navigate to URL and **Copy Link Address** for *Linux 64-bit*
2. Download the latest release with the command:

    `cd /tmp`

    `wget URL`

3. Extract contents

    `sudo unzip terraform...`

4. Find the helm binary in the unpacked directory, and move it to its desired destination

    `sudo mv terraform /usr/local/bin`

5. Validate Terraform

    `terraform version`
    
### [Terragrunt](https://terragrunt.gruntwork.io/docs/getting-started/install/)

1. Navigate to URL from above and follow instructions provided.

### [AWS CLI](https://aws.amazon.com/cli/)

*Run from tmp directory*

    `cd /tmp`

1. Navigate to [AWS CLI for Linux](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html#cliv2-linux-install) and follow instructions provided.

### [Azure CLI for Linux](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux?view=azure-cli-latest&pivots=apt")

1. Navigate to URL from above aand follow instructions provided.

## Git Config - Global Parameters

    `git config --global user.email "personal@email.address"`

    `git config --global user.name "Full Name"`

    `git config --global commit.gpgsign true`

**If you need to find your key, run the second command from the [Generate GPG Key](https://github.com/theseanodell/jumpbox#gpg-key) section to output your key.**

    `git config --global user.signingkey key_id`