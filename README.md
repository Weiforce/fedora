# fedora 常用命令

## 软件安装

 - android模拟器

    snap install anbox --beta --devmode
    
## 驱动程序

 - nvdia driver

    编辑 /etc/nvidia-container-runtime/config.toml and change #no-cgroups=false to no-cgroups=true
    
 - nvidia container driver

    wget -O /etc/yum.repos.d/inttf.repo https://rpms.if-not-true-then-false.com/inttf.repo
    # vi /etc/yum.repos.d/inttf.repo 
    # change fedora35 to fedora34

## build tools

    rpm-ostree install @development-tools @development-libraries

## 输入法

    rpm-ostree install *jidian*

## 笔记本盒盖不关机

    sudo vi /etc/systemd/logind.conf
    HandleLidSwitch ignore

## 自动登录用户

    打开系统设置=>用户=>单击图标 Automatic Login
    sudo vi /etc/gdm/custom.conf
    [daemon]
    AutomaticLoginEnable=true
    AutomaticLogin=mz2

## 安装常用库

    rpm-ostree install npm
    pip install celery flower

## 从 wayland 切换 x11

    sudo vi /etc/gdm/custom.conf
    [daemon]
    WaylandEnable=false
    DefaultSession=gnome-xorg.desktop

## 开机启动 APP

    mkdir ~/.config/autostart
    cp /usr/share/applications/rustdesk.desktop ~/.config/autostart
