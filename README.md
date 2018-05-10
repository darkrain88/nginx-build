# Hakase-nginx
**My nginx build files.**

## Please install dependency library.
- CentOS / Red Hat : yum install jemalloc-devel libuuid-devel libatomic libatomic_ops-devel expat-devel unzip autoconf automake libtool gd-devel geoip-devel gcc-c++ curl
- Ubuntu / Debian - apt install libjemalloc-dev uuid-dev libatomic1 libatomic-ops-dev expat unzip autoconf automake libtool libgd-dev libgeoip-dev g++ curl

## How to Install?
1. Install dependency library. (If you have already install it, omit it.)
2. Edit for config.inc file. (SERVER_HEADER, Modules, ETC.)
3. Run ./auto.sh
4. Install [systemctl file](https://www.nginx.com/resources/wiki/start/topics/examples/systemd/) (If you have already install it, omit it.)
5. Check version and error test : **nginx -v; nginx -t;**
5. systemctl restart nginx
6. **The END!!**

## Features
- Auto SSL Cipher settings
    - **The following information is preset. Do not set it yourself unless you need it.**
    - ssl_protocols
    - ssl_ciphers
    - ssl_prefer_server_ciphers
    - ssl_ecdh_curve
    - DO NOT USE ssl_dhparam. not required.
- TLS v1.3 (draft-23)
    - Use OpenSSL-1.1.1-pre3 (**draft 23**)
    - Use OpenSSL Equal Preference Patch ([BoringSSL](https://github.com/google/boringssl) & [CentminMod](https://centminmod.com/))
- Prefers ChaCha20 suites with clients that don't have AES-NI (e.g., Android devices)	
- More library!
    - headers_more_nginx_module
    - Google PageSpeed for nginx
    - and the other.
- Hpack, SSL Dynamic TLS Records Support. (Thanks to cloudflare!)

## Upcoming Features
- Support TLS v1.3 (not draft)
- Auto build (rpm, deb, etc.)
- ETC.
