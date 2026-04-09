![Downloads](https://img.shields.io/github/downloads/Slava-Shchipunov/awg-openwrt/total)

# Пакеты amneziawg для роутеров с прошивкой OpenWRT

## Автоматическая настройка AmneziaWG для OpenWRT версии 23.05.0 и более новых
1) Если ваш роутер обладает достаточным объмом доступной ROM, рекомендую воспользоваться скриптом, описанным ниже, только для установки нужных пакетов, а для точечной маршрутизации траффика в туннель использовать podkop от пользователя [@itdoginfo](https://github.com/itdoginfo) - тут в [документации](https://podkop.net/docs/tunnels/awg_settings/) описан процесс настройки

2) Если вам нужно только установить пакеты, я добавил скрипт amneziawg-install - он автоматически скачает пакеты из этого репозитория под ваше устройство (только для стабильной версии OpenWRT), а также предложит сразу настроить интерфейс с протоколом AmneziaWG. Если пользователь согласится, нужно будет ввести параметры конфига, которые запросит скрипт. При этом скрипт создаст интерфейс, настроит для него правила фаерволла, а также **включит перенаправление всего траффика через тунель AmneziaWG** (установит в настройках Peer галочку Route Allowed IPs).
Для запуска скрипта подключитесь к роутеру по SSH, введите команду и следуйте инструкциям на экране:
```
sh <(wget --no-check-certificate -O - https://raw.githubusercontent.com/guglovich/awg-openwrt-sf21-snapshot/refs/heads/master/amneziawg-install.sh)
```



# AmneziaWG для BPI-RV2 — сборка OpenWrt Snapshot

>  [Read in English](README.md)

**Платформа:** siflower / sf21 · riscv64_generic

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
