# Installation
- Install 
```
yum install git
```

- Initial configuration
```
# Setup username & email
git config --global user.name "Kien NT"
git config --global user.email neeikgnurt@gmail.com

# Choose default editor
git config --global core.editor vi

# List all configuration
git config --list
```

- Link github account via SSH
```
# Create $ Add ssh key
ssh-keygen -t rsa
ls ~/.ssh/
ssh-agent -s
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub

# Copy key to github
- Go to https://github.com/settings/ssh
- Add SSH key just generated
```

# Git basic
- Create new repo on github page

- Clone
```
# SSH
git clone git@github.com:neeik11/demo.git

# HTTPS
git clone https://github.com/neeik11/demo.git
```

- Add, commit, push & pull
```
# Add
git add <filename>
git add *

# Commit 
git commit <filename> -m "changed by kiennt"
git commit *

# Push
git push origin master

# Pull
git pull
```

