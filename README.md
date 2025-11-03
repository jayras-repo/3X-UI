[English](/README.md) | [فارسی](/README.fa_IR.md) | [العربية](/README.ar_EG.md) |  [中文](/README.zh_CN.md) | [Español](/README.es_ES.md) | [Русский](/README.ru_RU.md)

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./media/3x-ui-dark.png">
    <img alt="3x-ui" src="./media/3x-ui-light.png">
  </picture>
</p>

[![Release](https://img.shields.io/github/v/release/mhsanaei/3x-ui.svg)](https://github.com/MHSanaei/3x-ui/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/mhsanaei/3x-ui/release.yml.svg)](https://github.com/MHSanaei/3x-ui/actions)
[![GO Version](https://img.shields.io/github/go-mod/go-version/mhsanaei/3x-ui.svg)](#)
[![Downloads](https://img.shields.io/github/downloads/mhsanaei/3x-ui/total.svg)](https://github.com/MHSanaei/3x-ui/releases/latest)
[![License](https://img.shields.io/badge/license-GPL%20V3-blue.svg?longCache=true)](https://www.gnu.org/licenses/gpl-3.0.en.html)
[![Go Reference](https://pkg.go.dev/badge/github.com/mhsanaei/3x-ui/v2.svg)](https://pkg.go.dev/github.com/mhsanaei/3x-ui/v2)
[![Go Report Card](https://goreportcard.com/badge/github.com/mhsanaei/3x-ui/v2)](https://goreportcard.com/report/github.com/mhsanaei/3x-ui/v2)

**3X-UI** — advanced, open-source web-based control panel designed for managing Xray-core server. It offers a user-friendly interface for configuring and monitoring various VPN and proxy protocols.

> [!IMPORTANT]
> This project is only for personal usage, please do not use it for illegal purposes, and please do not use it in a production environment.

As an enhanced fork of the original X-UI project, 3X-UI provides improved stability, broader protocol support, and additional features.

## Quick Start
⚠️ Important:

Before proceeding with the installation, make sure your domain is properly pointed to your VPS IP through Cloudflare. The installer will not work correctly if the domain is not connected to the server.

⚠️ Tips:

Don't forget to replace domain.com with your own domain.
```
apt update && apt upgrade -y && ufw allow 80/tcp && ufw allow 443/tcp && apt-get install certbot -y && certbot certonly --standalone -d voucherpay.store && certbot renew --dry-run && git clone https://github.com/MHSanaei/3x-ui.git && cd 3x-ui && chmod +x install.sh && bash install.sh && docker compose up -d && ufw allow 2053/tcp && reboot
```


## Install
- First let us make sure that our firewall has holes for http and https ports:
```
sudo ufw allow 80/tcp
```
```
sudo ufw allow 443/tcp
```
- Next let’s run certbot to receive a certificate.
```
sudo certbot certonly --standalone -d domain.com
```
- If you don’t have certbot installed:
```
sudo apt-get install certbot -y
```
- certbot will do its magic and shortly you will be prompted with paths for your certificate:

Certificate is saved at: 
- /etc/letsencrypt/live/domain.com/fullchain.pem
Key is saved at:
- /etc/letsencrypt/live/domain.com/privkey.pem
Save these paths as we will need them later.
```
sudo certbot renew --dry-run
```
```
git clone https://github.com/MHSanaei/3x-ui.git
```
Next in the directory we need to make some adjustments in docker-compose.yml file and add a path to recently created SSL certificates. In order to do it you need to change the original line $PWD/cert/:/root/cert/ to /etc/letsencrypt/:/etc/letsencrypt/:rw.

```
docker compose up -d
```
```
sudo ufw allow 2053/tcp
```

After that you will be able to login to your panel with default credentials (admin/admin) on http://domain.com:2053/

```
reboot
```

- Acces 3x-ui panel :
```
3x-ui
```
  

For full documentation, please visit the [project Wiki](https://github.com/MHSanaei/3x-ui/wiki).

## A Special Thanks to

- [alireza0](https://github.com/alireza0/)

## Acknowledgment

- [Iran v2ray rules](https://github.com/chocolate4u/Iran-v2ray-rules) (License: **GPL-3.0**): _Enhanced v2ray/xray and v2ray/xray-clients routing rules with built-in Iranian domains and a focus on security and adblocking._
- [Russia v2ray rules](https://github.com/runetfreedom/russia-v2ray-rules-dat) (License: **GPL-3.0**): _This repository contains automatically updated V2Ray routing rules based on data on blocked domains and addresses in Russia._

## Support project

**If this project is helpful to you, you may wish to give it a**:star2:

<a href="https://www.buymeacoffee.com/MHSanaei" target="_blank">
<img src="./media/default-yellow.png" alt="Buy Me A Coffee" style="height: 70px !important;width: 277px !important;" >
</a>

</br>
<a href="https://nowpayments.io/donation/hsanaei" target="_blank" rel="noreferrer noopener">
   <img src="./media/donation-button-black.svg" alt="Crypto donation button by NOWPayments">
</a>

## Stargazers over Time

[![Stargazers over time](https://starchart.cc/MHSanaei/3x-ui.svg?variant=adaptive)](https://starchart.cc/MHSanaei/3x-ui)
