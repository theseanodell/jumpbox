# jumpbox

Generate SSH Key
ssh-keygen -b 4096

Add key to Github
Add Key to Gitlab

cat ~/.ssh/id_rsa.pub
cat ~/.ssh/id_rsa

Create GPG Key
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
 Add 2nd Email
gpg --edit-key “key_id”
gpg> adduid
gpg> save

gpg --armor --export “key_id”
export GPG_TTY=$(tty)

Add key to Github
Add Key to Gitlab

Github CLI
gh auth login

Git Config Global

git config --global user.signingkey “key_id”
git config --global user.email "sean.odell@cloudychance.io"
git config --global user.name "Sean O'Dell"
git config --global commit.gpgsign true
