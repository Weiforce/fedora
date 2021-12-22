# fedora 常用命令

## adop

- https://stackoverflow.com/questions/44166269/libgl-error-failed-to-load-driver-swrast-in-docker-container
- https://github.com/gklingler/docker3d

## 软件配置

    设置 -> 键盘 -> 极点加入 -> ctrl + space -> shift + space

## 软件安装
 
## 驱动程序

## 库安装 for adop

    rpm-ostree install mesa-libGLU freeimage assimp

### nvdia driver

    rpm-ostree install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
    rpm-ostree install akmod-nvidia xorg-x11-drv-nvidia xorg-x11-drv-nvidia-cuda
    rpm-ostree kargs --append=rd.driver.blacklist=nouveau --append=modprobe.blacklist=nouveau --append=nvidia-drm.modeset=1
    
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/libnvidia-container-devel-1.3.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/libnvidia-container-static-1.3.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/libnvidia-container-tools-1.3.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/libnvidia-container1-1.3.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/libnvidia-container1-debuginfo-1.3.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/nvidia-container-runtime-3.4.0-1.x86_64.rpm
    wget https://rpms.if-not-true-then-false.com/fedora34/x86_64/nvidia-container-toolkit-1.3.0-2.x86_64.rpm
    rpm-ostree install libnvidia-container1-1.3.0-1.x86_64.rpm libnvidia-container1-debuginfo-1.3.0-1.x86_64.rpm libnvidia-container-devel-1.3.0-1.x86_64.rpm libnvidia-container-static-1.3.0-1.x86_64.rpm libnvidia-container-tools-1.3.0-1.x86_64.rpm nvidia-container-runtime-3.4.0-1.x86_64.rpm nvidia-container-toolkit-1.3.0-2.x86_64.rpm 
    
    sudo sed -i 's/#no-cgroups = false/no-cgroups = true/' /etc/nvidia-container-runtime/config.toml

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
