# debian 11 bullseye

```
echo root:linux | chpasswd
sed -i '/^#PermitRootLogin/c\PermitRootLogin yes' /etc/ssh/sshd_config
cat > /etc/apt/sources.list << EOF
deb https://mirrors.aliyun.com/debian bullseye main contrib
deb-src https://mirrors.aliyun.com/debian bullseye main contrib

deb https://mirrors.aliyun.com/debian bullseye-updates main contrib
deb-src https://mirrors.aliyun.com/debian bullseye-updates main contrib

deb https://mirrors.aliyun.com/debian bullseye-backports main contrib
deb-src https://mirrors.aliyun.com/debian bullseye-backports main contrib

deb https://mirrors.aliyun.com/debian-security/ bullseye-security main contrib
deb-src https://mirrors.aliyun.com/debian-security/ bullseye-security main contrib
EOF

apt-get update
apt-get install -y vim lrzsz tmux build-essential xrdp

sed -i 's/^autologin-user=pi/#autologin-user=pi/g' /etc/lightdm/lightdm.conf
sed -i 's/^autologin-user-timeout=0/#autologin-user-timeout=0/g' /etc/lightdm/lightdm.conf
sed -i 's/^session-wrapper=\/etc\/X11\/Xsession/#session-wrapper=\/etc\/X11\/Xsession/g' /etc/lightdm/lightdm.conf

cat > ~/.bashrc << EOF
# ~/.bashrc: executed by bash(1) for non-login shells.

# Note: PS1 and umask are already set in /etc/profile. You should not
# need this unless you want different defaults for root.
# PS1='${debian_chroot:+($debian_chroot)}\h:\w\$ '
# umask 022

# You may uncomment the following lines if you want `ls' to be colorized:
# export LS_OPTIONS='--color=auto'
# eval "$(dircolors)"
# alias ls='ls $LS_OPTIONS'
# alias ll='ls $LS_OPTIONS -l'
# alias l='ls $LS_OPTIONS -lA'
#
# Some more alias to avoid making mistakes:
# alias rm='rm -i'
# alias cp='cp -i'
# alias mv='mv -i'
# github.com/yifengyou/bash
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l.='ls -d .* -a --color=auto'
alias ll='ls -l -h -a --color=auto'
alias ls='ls -a --color=auto'
alias cp='cp -i'
alias mv='mv -i'
alias rm='rm -i'
alias xzegrep='xzegrep --color=auto'
alias xzfgrep='xzfgrep --color=auto'
alias xzgrep='xzgrep --color=auto'
alias zegrep='zegrep --color=auto'
alias zfgrep='zfgrep --color=auto'
alias zgrep='zgrep --color=auto'
alias rpmbuild='rpmbuild --define "_topdir $(pwd)"'

# History setting
export PROMPT_COMMAND="history -a"
export HISTTIMEFORMAT="%F %T "
export HISTSIZE=10000

# PS1
PS1='\[\e[32;1m\][\[\e[31;1m\]\u\[\e[33;1m\]@\[\e[35;1m\]\h\[\e[36;1m\] \w\[\e[32;1m\]]\[\e[37;1m\]\\$\[\e[0m\] '

alias linux='cd /linux/linux.git'
alias linux2='cd /linux/linux-2.git'
alias linux3='cd /linux/linux-3.git'
alias linux4='cd /linux/linux-4.git'
alias linux5='cd /linux/linux-5.git'
alias linux6='cd /linux/linux-6.git'
alias ctl2='cd /linux/linux-ctl2.git'
alias ctl3='cd /linux/linux-ctl3.git'
alias ctl4='cd /linux/linux-ctl4.git'
alias linuxbuild='cd /linux/linux.git-build-x86_64'
alias linux2build='cd /linux/linux-2.git-build-x86_64'
alias linux3build='cd /linux/linux-3.git-build-x86_64'
alias linux4build='cd /linux/linux-4.git-build-x86_64'
alias linux5build='cd /linux/linux-5.git-build-x86_64'
alias linux6build='cd /linux/linux-6.git-build-x86_64'
alias ctl2build='cd /linux/linux-ctl2.git-build-x86_64'
alias ctl3build='cd /linux/linux-ctl3.git-build-x86_64'
alias ctl4build='cd /linux/linux-ctl4.git-build-x86_64'
EOF






```
