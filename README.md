# misc-pacur: misc package repository

Misc package repository for centos-7 and ubuntu-xenial

### centos-7

```
sudo tee -a /etc/yum.repos.d/pritunl-misc.repo << EOF
[pritunl-misc]
name=Pritunl Misc Repository
baseurl=https://repo.pritunl.com/misc/yum/centos/7/
gpgcheck=1
enabled=1
priority=1
EOF

gpg --keyserver hkp://keyserver.ubuntu.com --recv-keys 7568D9BB55FF9E5287D586017AE645C0CF8E292A
gpg --armor --export 7568D9BB55FF9E5287D586017AE645C0CF8E292A > key.tmp; sudo rpm --import key.tmp; rm -f key.tmp
sudo yum -y install tmux mosh
```

### ubuntu-xenial

```
sudo tee -a /etc/apt/sources.list.d/pritunl-misc.list << EOF
deb http://repo.pritunl.com/misc/apt xenial main
EOF

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv 7568D9BB55FF9E5287D586017AE645C0CF8E292A
sudo apt update
sudo apt install tmux mosh
```
