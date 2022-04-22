# Assetto Corsa Competizione "Rasern" Server
## Server settings
- Google Compute Engine
- 2 High-end vCPUs, 2 Gb RAM, 10 GB HDD with Ubuntu Minimal
- Set network tag: acc (allows ingress and egress for TCP:9601 and UDP:9600)

## First time VM setup

- Execute: `sudo apt update && sudo apt install -y nano cron git wine-development && sudo dpkg --add-architecture i386 && sudo apt update && sudo apt install -y wine32-development && sudo apt autoremove -y && git clone https://github.com/RRothfeld/rasernserver.git && crontab -e`
- Add to crontab: `@reboot git -C ./rasernserver pull && ( cd rasernserver && exec wine accServer.exe )`