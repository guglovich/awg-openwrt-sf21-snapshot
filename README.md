# AmneziaWG for BPI-RV2 — OpenWrt Snapshot Build

>  [Читать на русском](README.ru.md)

**Platform:** siflower / sf21 · riscv64_generic

---

## About

This repository contains pre-built **AmneziaWG** packages for the Banana Pi BPI-RV2 router running OpenWrt **snapshot** builds. The official releases only cover stable versions — these packages fill the gap for snapshot users.

---
## Install

```
sh <(wget --no-check-certificate -O - https://raw.githubusercontent.com/guglovich/awg-openwrt-sf21-snapshot/refs/heads/master/amneziawg-install.sh)
```

---

## Packages

| Component | Package |
|---|---|
| Kernel module | `kmod-amneziawg` |
| Userspace tools | `amneziawg-tools` |
| LuCI protocol | `luci-proto-amneziawg` |
| Target | `siflower / sf21` |

> ⚠️ The kernel module must match your running kernel version exactly. If your snapshot was updated since the build, re-run the workflow or flash the latest snapshot image first.

---

## Install

```sh
# from your PC
scp *.apk root@192.168.1.1:/tmp/

# on the router via SSH
apk add --allow-untrusted /tmp/kmod-amneziawg_*.apk
apk add --allow-untrusted /tmp/amneziawg-tools_*.apk
apk add --allow-untrusted /tmp/luci-proto-amneziawg_*.apk
```

---

## References

- Original repo: [Slava-Shchipunov/awg-openwrt](https://github.com/Slava-Shchipunov/awg-openwrt)
- Setup guide: [podkop.net/docs/tunnels/awg_settings](https://podkop.net/docs/tunnels/awg_settings/)
