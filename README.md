# fedora 常用设置

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
