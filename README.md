# ubuntu-in-termux
This is a script by which you can install Ubuntu in your termux application without rooted phone

# FULLY UPDATED TO UBUNTU 19.04 DISCO

Steps
1. Update termux: apt-get update && apt-get upgrade -y
2. Install wget: apt-get install wget -y
3. Install proot: apt-get install proot -y
4. Install git: apt-get install git -y
5. Go to HOME folder: cd ~
6. Download script: git clone https://github.com/MFDGaming/ubuntu-in-termux.git
7. Go to script folder: cd ubuntu-in-termux
8. Give execution permission: chmod +x ubuntu.sh
9. Run script: ./ubuntu.sh
10. Fix resolv.conf: cp ~/ubuntu-in-termux/resolv.conf ~/ubuntu-in-termux/ubuntu-fs/etc/
11. Now just start ubuntu: ./start.sh

在非 termux 环境下，建议手动执行
1. 下载 ubuntu 镜像： wget http://cdimage.ubuntu.com/ubuntu-base/releases/18.04.3/release/ubuntu-base-18.04.3-base-amd64.tar.gz -O ubuntu.tar.gz
2. 解压ubuntu镜像：mkdir ubuntu-fs && cd ubuntu-fs && tar xzf ../ubuntu.tar.gz
3. 用包管理器按照 proot，或者下载编译好的 proot：https://github.com/proot-me/proot-static-build/releases
4. 执行proot： proot -0 -r ubuntu-fs -b /dev -b /proc -b ubuntu-fs/tmp:/dev/shm /usr/bin/env -i HOME=/root PATH=/usr/local/sbin:/usr/local/bin:/bin:/usr/bin:/sbin:/usr/sbin:/usr/games:/usr/local/games TERM=screen LANG=C.UTF-8 /bin/bash --login
