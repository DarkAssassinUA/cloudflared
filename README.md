Cloudflare Tunnel client for mipsle devices

Tested on Keenetic Viva (KN19-10)

Current version 2024.1.5

Compiled binary from https://github.com/cloudflare/cloudflared to mipsle devices.
Tested on Keenetic Viva(KN-1910) with Entware

Usage:

-S99cloudflared put to /etc/init.d folder on opkg drive and replace in 17 string %yourtokenhere% with you token obtained in Cloudflare Zero Trust Dashboard

-cloudflared put to /home/ folder and make in ssh console chmod +x /opt/home/cloudflared

after that - just reboot router,after 60 seconds cloudflared will be online and visible in Cloudflare Zero Trust Dashboard


