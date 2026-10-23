# Mellonbot releases

Signed builds of the Mellonbot CLI, the agent that connects a Linux server to [Mellonbot](https://mellonbot.app). The source lives in a private repository; this one only holds releases.

## Install

Run on the server over SSH. Get the token from the server step in the Mellonbot dashboard.

```sh
curl -fsSL -o mellonbot https://github.com/mellonbot-app/releases/releases/latest/download/mellonbot_linux_amd64
sudo install -m 0755 mellonbot /usr/local/bin/mellonbot
sudo mellonbot register --token <token>
```

On arm64 servers download `mellonbot_linux_arm64` instead. Supported: Ubuntu 22.04 / 24.04 and Debian 12 with systemd.

Installed agents update themselves from the latest release here. Every release has `checksums.txt` signed with Mellonbot's Ed25519 key (`checksums.txt.sig`); the agent refuses anything that doesn't verify.
