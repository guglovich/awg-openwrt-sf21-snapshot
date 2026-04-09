# AmneziaWG для BPI-RV2 — сборка OpenWrt Snapshot

>  [Read in English](README.md)

**Платформа:** siflower / sf21 · riscv64_generic

---

## Установка

```
sh <(wget --no-check-certificate -O - https://raw.githubusercontent.com/guglovich/awg-openwrt-sf21-snapshot/refs/heads/master/amneziawg-install.sh)
```
---

## О проекте

Этот репозиторий содержит собранные пакеты **AmneziaWG** для роутера Banana Pi BPI-RV2 на OpenWrt **snapshot**. Официальные релизы поддерживают только стабильные версии — эти пакеты закрывают пробел для пользователей снапшотов.

---

## Пакеты

| Компонент | Пакет |
|---|---|
| Модуль ядра | `kmod-amneziawg` |
| Утилиты | `amneziawg-tools` |
| LuCI протокол | `luci-proto-amneziawg` |
| Платформа | `siflower / sf21` |

> ⚠️ Модуль ядра должен точно совпадать с версией запущенного ядра. Если снапшот обновился после сборки — перезапусти workflow или сначала прошей актуальный снапшот.

---

## Установка

```sh
# с компьютера
scp *.apk root@192.168.1.1:/tmp/

# на роутере через SSH
apk add --allow-untrusted /tmp/kmod-amneziawg_*.apk
apk add --allow-untrusted /tmp/amneziawg-tools_*.apk
apk add --allow-untrusted /tmp/luci-proto-amneziawg_*.apk
```

---

## Ссылки

- Оригинальный репо: [Slava-Shchipunov/awg-openwrt](https://github.com/Slava-Shchipunov/awg-openwrt)
- Настройка: [podkop.net/docs/tunnels/awg_settings](https://podkop.net/docs/tunnels/awg_settings/)
