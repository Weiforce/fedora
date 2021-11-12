# fedora 常用设置

## 从wayland 切换 x11
sudo vi /etc/gdm/custom.conf
[daemon]
WaylandEnable=false
DefaultSession=gnome-xorg.desktop

## 开机启动 APP
mkdir ~/.config/autostart
mv /usr/share/applications/rustdesk.desktop ~/.config/autostart
