---
title: "HTTPie on CentOS / RHEL"
tags: [httpie, packaging, centos, rhel, yum, epel]
category: "packaging"
created: "2024-01-01"
updated: "2026-10-20"
source: "external"
type: "index"
status: "stable"
lifecycle: "active"
---

# 💡 概述

Welcome to the documentation about **packaging HTTPie for CentOS and RHEL**.

- If you do not know HTTPie, have a look [here](https://httpie.io/cli).
- If you are looking for HTTPie installation or upgrade instructions on CentOS, then you can find them on [that page](https://httpie.io/docs#centos-and-rhel).
- If you are looking for technical information about the HTTPie packaging on CentOS, then you are in a good place.

This document contains technical details, where we describe how to create a patch for the latest HTTPie version for CentOS. They apply to RHEL as well, and any RHEL-derived distributions like ClearOS, Oracle Linux, etc. We will discuss setting up the environment, installing development tools, installing and testing changes before submitting a patch downstream.

The current maintainer is [Mikel Olasagasti](https://github.com/kaxero).

---

## ⚡ 功能

Same as [Fedora](../linux-fedora/README.md#overall-process).

---

## 📊 指标

「待补充」

---

## 🏛️ 设计

### Q/A with Mikel

Q: What should we do to help seeing a new version on CentOS?

A: When a new release is published Miro and I get notified by [release-monitoring](https://release-monitoring.org/project/1337/), that fills a BugZilla ticket reporting a new version being available.

The system also tries to create a simple patch to update the spec file, but in the case of CentOS it needs some manual revision. For example for 2.5.0 `defusedxml` dep is required. Maybe with CentOS-9 and some new macros that are available now in Fedora it can be automated same way. But even the bump can be automated, maintainers should check for license changes, new binaries/docs/ and so on.

---

## 📁 目录

「待补充」

---

## 🔗 资源

- [Mikel Olasagasti (maintainer)](https://github.com/kaxero)
- [release-monitoring](https://release-monitoring.org/project/1337/)
- [Fedora packaging](../linux-fedora/README.md)

---

## 🚀 快速开始

「待补充」

---

## ⚙️ 技术栈

- CentOS / RHEL (yum/dnf)
- EPEL
- RPM spec files