# Linux-Cacule Kernels for several architectures (armv7/aarch64 and x86_64)

## General Informations

    - Linux-cacule is the stable kernel
    - The linux-cacule-rdb is still a expermiental patch.
    - Follow the readme, the sysctl options can improve much your expierence!!!

### amd64 /  x86_64

    # Linux 5.12.y
        - linux-cacule                         https://aur.archlinux.org/packages/linux-cacule/
        - linux-cacule-rdb                     https://aur.archlinux.org/packages/linux-cacule-rdb/
    # Linux 5.11.y
        - linux-hardened-cacule                https://aur.archlinux.org/packages/linux-hardened-cacule/
    # Linux 5.13-rc (not updated right now)
        - linux-cacule-rc                      https://aur.archlinux.org/packages/linux-cacule-rc/
        - linux-cacule-rdb-rc                  https://aur.archlinux.org/packages/linux-cacule-rdb-rc/

 ---
 ### RT-KERNELS

    ä linux-xanmod-cacule-rt 5.11.y             https://aur.archlinux.org/packages/linux-xanmod-cacule-rt/
    # linux-xanmod-cacule-rt 5.10.y             https://aur.archlinux.org/packages/linux-xanmod-cacule-rt-stable/


- When building the kernel, you can edit the PKGBUILD to your prefences regarding the user specific wishes
- Also at building the kernel, you will be asked for some things like your cpu architecture, disabling debug settings for better performance, ...

### aarch64/armv7h

    # Linux 5.11.y
        - linux-raspberrypi4-cacule-stable      https://aur.archlinux.org/packages/linux-raspberrypi4-cacule-stable/
    # Linux 5.10.y
        - linux-raspberrypi4-cacule             https://aur.archlinux.org/packages/linux-raspberrypi4-cacule/


#### Some infos for building  arm devices:
    -  it is automaticly collecting your architecture, so you can use the pkgbuild for armv7h/aarch64 without changes
    -  All kernels are tested and working


## General Informations

### Tips & Tricks:

You can tune the scheduler with following commands:

             ## Cacule-Settings ## 
            kernel.sched_interactivity_factor=32768
            kernel.sched_max_lifetime_ms=22000
            kernel.sched_nr_fork_threshold=3
            kernel.sched_fake_interactive_win_time_ms=1000
            kernel.sched_harsh_mode_enabled=0

           ### Network-Settings ##

            net.core.netdev_max_backlog = 16384
            net.core.somaxconn = 8192
            net.core.rmem_default = 1048576
            net.core.rmem_max = 16777216
            net.core.wmem_default = 1048576
            net.core.wmem_max = 16777216
            net.core.optmem_max = 65536
            net.ipv4.tcp_rmem = 4096 1048576 2097152
            net.ipv4.tcp_wmem = 4096 65536 16777216
            net.ipv4.udp_rmem_min = 8192
            net.ipv4.udp_wmem_min = 8192
            net.ipv4.tcp_fastopen = 3
            net.ipv4.tcp_keepalive_time = 60
            net.ipv4.tcp_keepalive_intvl = 10
            net.ipv4.tcp_keepalive_probes = 6
            net.ipv4.conf.default.log_martians = 1
            net.ipv4.conf.all.log_martians = 1
            net.ipv4.tcp_mtu_probing = 1
            net.ipv4.tcp_syncookies = 1
            net.core.default_qdisc = cake
            net.ipv4.tcp_congestion_control = bbr2


## prebuilt Kernels

Im providing a fileserver where i upload my builded kernels, if you want to use them just  watch their:

https://repo.ptr1337.dev

##  more explained Informations for the cacule scheduler

Here you find the repo from the creator of the scheduler:

https://github.com/hamadmarri/cacule-cpu-scheduler

# Credits
Hamad Marri for his cacule scheduler https://github.com/hamadmarri
SirLucjan (Piotr Gorski) for his patches https://github.com/sirlucjan/kernel-patches
Arch
GarudaLinux
and all other Kernel Developers
