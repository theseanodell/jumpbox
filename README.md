# jumpbox

## Generate SSH Key
ssh-keygen -b 4096

Add key to Github
Add Key to Gitlab

cat ~/.ssh/id_rsa.pub
cat ~/.ssh/id_rsa

## Create GPG Key
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
Add 2nd Email
gpg --edit-key “key_id”
gpg> adduid
gpg> save

gpg --armor --export “key_id”

### Enable GPG TTY

`vim ~/.bashrc`

Add the following:

`# Enable GPG TTY`
`export GPG_TTY="$( tty )"`

Add key to Github
Add Key to Gitlab

## Install Packages, Software and Applications

### Zip

`sudo apt install zip`

### [Github CLI](https://cli.github.com/)

gh auth login

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

## Git Config Global

### Configure Git Global Parameters

`git config --global user.signingkey “key_id”`
`git config --global user.email "sean.odell@cloudychance.io"`
`git config --global user.name "Sean O'Dell"`
`git config --global commit.gpgsign true`
