---
title: "HTTPie on Debian / Ubuntu"
tags: [httpie, packaging, debian, ubuntu, apt, fpm]
category: "packaging"
created: "2024-01-01"
updated: "2026-10-20"
source: "external"
type: "index"
status: "stable"
lifecycle: "active"
---

# 💡 概述

Welcome to the documentation about **packaging HTTPie for Debian GNU/Linux**.

- If you do not know HTTPie, have a look [here](https://httpie.io/cli).
- If you are looking for HTTPie installation or upgrade instructions on Debian GNU/Linux, then you can find them on [that page](https://httpie.io/docs#debian-and-ubuntu).
- If you are looking for technical information about the HTTPie packaging on Debian GNU/Linux, then you are in a good place.

This document contains technical details, where we describe how to create a patch for the latest HTTPie version for Debian GNU/Linux. They apply to Ubuntu as well, and any Debian-derived distributions like MX Linux, Linux Mint, deepin, Pop!_OS, KDE neon, Zorin OS, elementary OS, Kubuntu, Devuan, Linux Lite, Peppermint OS, Lubuntu, antiX, Xubuntu, etc.

We create the standalone binaries (see [for more details](../../../extras/packaging/linux/)) and package them with [FPM](https://github.com/jordansissel/fpm)'s `dir` mode. The core `http`/`https` commands don't have any dependencies, but the `httpie` command (due to the underlying `httpie cli plugins` interface) explicitly depends to the system Python (through `python3`/`python3-pip`).

---

## ⚡ 功能

The [`Release as Standalone Linux Binary`](https://github.com/httpie/cli/actions/workflows/release-linux-standalone.yml) will be automatically triggered when a new release is created, and it will submit the `.deb` package as a release asset.

For making that asset available for all debian users, the release manager needs to go to the [`httpie/debian.httpie.io`](https://github.com/httpie/debian.httpie.io) repo and trigger the [`Update Index`](https://github.com/httpie/debian.httpie.io/actions/workflows/update-index.yml) action. It will automatically scrape all new debian packages from the release assets, properly update the indexes and create a new PR ([an example](https://github.com/httpie/debian.httpie.io/pull/1)) which then will become active when merged.

---

## 📊 指标

「待补充」

---

## 🏛️ 设计

- Standalone binaries via PyInstaller
- Wrapped with FPM `dir` mode
- Core commands have no runtime deps
- `httpie` command needs `python3`/`python3-pip`

---

## 📁 目录

「待补充」

---

## 🔗 资源

- [Release as Standalone Linux Binary](https://github.com/httpie/cli/actions/workflows/release-linux-standalone.yml)
- [debian.httpie.io](https://github.com/httpie/debian.httpie.io)
- [Update Index action](https://github.com/httpie/debian.httpie.io/actions/workflows/update-index.yml)
- [FPM](https://github.com/jordansissel/fpm)
- [Standalone Linux packages](../../../extras/packaging/linux/)

---

## 🚀 快速开始

「待补充」

---

## ⚙️ 技术栈

- Debian / Ubuntu (apt)
- FPM
- PyInstaller
- GitHub Actions