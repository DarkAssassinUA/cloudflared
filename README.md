Cloudflare Tunnel client for mipsle devices

Tested on Keenetic Viva (KN-1910)

Current version `2025.1.0`
Builded with Go `1.23.4`

WARNING: All software provided here is provided as is without any questions or complaints. Please direct all questions and complaints to the original cloudflared repository, this is just an assembly for miplse devices assembled from the source code without any changes. All open issues related to the work of cloudflared itself will be closed without response. You have been warned.

Compiled binary from https://github.com/cloudflare/cloudflared to mipsle devices.
Tested on Keenetic Viva(KN-1910)(Keenetic OS 4.2 Beta 3) with Entware

Usage:
Connect to OPKG SSH

`opkg install wget-ssl `
(if wget already exists and saying about http or ftp connection -  `opkg remove wget-nossl `

`wget -O /opt/etc/init.d/S99cloudflared https://raw.githubusercontent.com/DarkAssassinUA/cloudflared/main/S99cloudflared `


`nano /opt/etc/init.d/S99cloudflared` -- and replace `%yourtoken%` with your token obtain at Cloudflare Zero Trust Dashboard-Networks-Tunnels-Tunnel Name

`chmod +x /opt/etc/init.d/S99cloudflared`

`wget -O /opt/home/cloudflared https://github.com/DarkAssassinUA/cloudflared/raw/main/cloudflared`


`chmod +x /opt/home/cloudflared`

After that - just reboot router,after 60 seconds cloudflared will be online and visible in Cloudflare Zero Trust Dashboard


Or just


`/opt/etc/init.d/S99cloudflared start`


Build yourself:
If u wanna buid it urself - install Go Lang FIRST!!!
`apt update & apt upgrade`
next step is cloning cloudflared repo:
`git clone https://github.com/cloudflare/cloudflared & cd cloudflared`
build toolchain for building(lmao) cloudflared

`./.teamcity/install-cloudflare-go.sh`

if u see - 

`Installed Go for linux/amd64 in /tmp/go`
`Installed commands in /tmp/go/bin` - all ok

Next step is compiling cloudflared
`TARGET_ARCH=mipsle GOMIPS=softfloat make cloudflared`
after compiling - u can found `cloudflared` binary in folder

Updating:
if u wanna update `cloudflared`:
`cd cloudflared`
`git pull`
`TARGET_ARCH=mipsle GOMIPS=softfloat make cloudflared`
