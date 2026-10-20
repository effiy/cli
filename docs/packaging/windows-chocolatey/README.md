---
title: "HTTPie on Chocolatey"
tags: [httpie, packaging, chocolatey, windows]
category: "packaging"
created: "2024-01-01"
updated: "2026-10-20"
source: "external"
type: "index"
status: "stable"
lifecycle: "active"
---

# 💡 概述

Welcome to the documentation about **packaging HTTPie for Chocolatey**.

- If you do not know HTTPie, have a look [here](https://httpie.io/cli).
- If you are looking for HTTPie installation or upgrade instructions on Chocolatey, then you can find them on [that page](https://httpie.io/docs#chocolatey).
- If you are looking for technical information about the HTTPie packaging on Chocolatey, then you are in a good place.

This document contains technical details, where we describe how to create a patch for the latest HTTPie version for Chocolatey. We will discuss setting up the environment, installing development tools, installing and testing changes before submitting a patch downstream.

---

## ⚡ 功能

After having successfully built and tested the package, either trigger the [`Release on Chocolatey`](https://github.com/httpie/cli/actions/workflows/release-choco.yml) action to push it to the `Chocolatey` store or use the CLI:

```bash
# Replace 2.5.0 with the correct version
choco push httpie.2.5.0.nupkg -s https://push.chocolatey.org/ --api-key=API_KEY
```

Be aware that it might take multiple days until the release is approved, since it goes through multiple sets of reviews (some of them are done manually).

---

## 📊 指标

「待补充」

---

## 🏛️ 设计

「待补充」

---

## 📁 目录

「待补充」

---

## 🔗 资源

- [`Release on Chocolatey` action](https://github.com/httpie/cli/actions/workflows/release-choco.yml)

---

## 🚀 快速开始

```bash
# Clone
git clone --depth=1 https://github.com/httpie/cli.git
cd httpie/docs/packaging/windows-chocolatey

# Build
choco pack

# Check metadata
choco info httpie -s .

# Install
choco install httpie -y -dv -s "'.;https://community.chocolatey.org/api/v2/'"

# Test
http --version
https --version

# Remove
choco uninstall -y httpie
```

---

## ⚙️ 技术栈

- Chocolatey
- NuGet
- GitHub Actions