---
title: "HTTPie Release Process"
tags: [httpie, packaging, release, deployment]
category: "packaging"
created: "2024-01-01"
updated: "2026-10-20"
source: "external"
type: "index"
status: "stable"
lifecycle: "active"
---

# 💡 概述

Welcome on the documentation part of the **HTTPie release process**.

- If you do not know HTTPie, have a look [here](https://httpie.io/cli).
- If you are looking for HTTPie installation or upgrade instructions, then you can find all you need for your OS on [that page](https://httpie.io/docs#installation). In the case you do not find your OS, [let us know](https://github.com/httpie/cli/issues/).
- If you are looking for technical information about the HTTPie packaging, then you are at the good place.

You are looking at the HTTPie packaging documentation, where you will find valuable information about how we manage to release HTTPie to lots of OSes, including technical data that may be worth reading if you are a package maintainer.

---

## ⚡ 功能

The overall release process:

1. Bump the version identifiers in the following places:
    - `httpie/__init__.py`
    - `docs/packaging/windows-chocolatey/httpie.nuspec`
    - `CHANGELOG.md`
2. Commit your changes and make a PR against the `master`.
3. Merge the PR, and tag the last commit with your version identifier.
4. Make a GitHub release (by copying the text in `CHANGELOG.md`)
5. Push that release to PyPI (dispatch the `Release PyPI` GitHub action).
6. Once PyPI is ready, push the release to the Snap, Homebrew and Chocolatey with their respective actions.
7. Go to the [`httpie/debian.httpie.io`](https://github.com/httpie/debian.httpie.io) repo and trigger the package index workflow.

---

## 📊 指标

A more complete state of deployment can be found on [repology](https://repology.org/project/httpie/versions), including unofficial packages.

---

## 🏛️ 设计

|                                           OS | Maintainer     |
| -------------------------------------------: | -------------- |
|       [Arch Linux, and derived](linux-arch/) | trusted person |
|   [CentOS, RHEL, and derived](linux-centos/) | trusted person |
|                      [Fedora](linux-fedora/) | trusted person |
| [Debian, Ubuntu, and derived](linux-debian/) | **HTTPie**     |
|                 [Homebrew, Linuxbrew](brew/) | **HTTPie**     |
|                      [Snapcraft](snapcraft/) | **HTTPie**     |
|  [Windows -- Chocolatey](windows-chocolatey/) | **HTTPie**     |

:new: You do not find your system or you would like to see HTTPie supported on another OS? Then [let us know](https://github.com/httpie/cli/issues/).

---

## 📁 目录

| 路径 | 说明 |
|------|------|
| `linux-arch/` | Arch Linux packaging |
| `linux-centos/` | CentOS/RHEL packaging |
| `linux-fedora/` | Fedora packaging |
| `linux-debian/` | Debian/Ubuntu packaging |
| `brew/` | Homebrew/Linuxbrew packaging |
| `snapcraft/` | Snapcraft packaging |
| `windows-chocolatey/` | Chocolatey packaging |

---

## 🔗 资源

- [HTTPie CLI](https://httpie.io/cli)
- [Installation docs](https://httpie.io/docs#installation)
- [GitHub Issues](https://github.com/httpie/cli/issues/)
- [repology](https://repology.org/project/httpie/versions)

---

## 🚀 快速开始

### Company-specific tasks

- Blank the `master_and_released_docs_differ_after` value in [config.json](https://github.com/httpie/cli/blob/master/docs/config.json).
- Update the [contributors list](../contributors).
- Update the HTTPie version bundled into [Termible](https://termible.io/) ([example](https://github.com/httpie/termible/pull/1)).

---

## ⚙️ 技术栈

- Python
- PyPI
- GitHub Actions
- Snap, Homebrew, Chocolatey, FPM