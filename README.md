# fedora 常用命令

## 软件安装

 - android模拟器

    snap install anbox --beta --devmode
    
## 驱动程序

 - nvdia driver

    rpm-ostree install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
    rpm-ostree remove akmod-nvidia xorg-x11-drv-nvidia-cuda
    rpm-ostree install akmod-nvidia xorg-x11-drv-nvidia-cuda

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
