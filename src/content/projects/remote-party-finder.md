---
title: "Remote Party Finder"
slug: remote-party-finder
published: 2026-11-17
draft: false
order: 95
description: "国服《最终幻想 XIV》跨服招募板（Party Finder）。Fork 自 Anna Clemens 的 Remote Party Finder，服务端用 Rust 实现，配套 MongoDB 与 Web API，可在线浏览与筛选各服招募。"
image: "images/remote-party-finder.avif"
status: "published"
tags:
  - FF14
  - Rust
  - MongoDB
  - 招募板
link:
  - label: "GitHub"
    icon: "fa7-brands:github"
    value: "https://github.com/LittleNightmare/remote-party-finder/"
  - label: "网站"
    icon: "material-symbols:language"
    value: "https://xivpf.littlenightmare.top/"
---

## 项目简介

Remote Party Finder 是国服《最终幻想 XIV》的**跨服招募板（Party Finder）**，让你不用切服就能浏览各大服务器的招募信息。本项目基于 [Anna Clemens](https://git.anna.lgbt/ascclemens/remote-party-finder) 的 Remote Party Finder 分支，针对国服环境做了适配构建。

服务端使用 **Rust** 实现，配套 **MongoDB** 存储与 Web API；网页前端可在线按资料片、任务、职业等条件浏览与筛选招募。（前端仓库：[remote-party-finder-frontend](https://github.com/Cindy-Master/remote-party-finder-frontend)。）

## 主要特性

- **跨服浏览**：聚合各国服服务器的招募信息，无需登录游戏即可查看。
- **Web API**：同时提供 v1（Legacy）与 v2（phase 1）读接口，v2 以纯 ID 形式返回招募资源，便于前端自行解析标签。
- **分类与任务编码**：解析客户端 `CrossRealmListing` 数据包中的 `category` / `duty` / `duty_type` 字段，覆盖讨伐战、深层迷宫、金碟游乐场、V&amp;C 迷宫等分类。
- **国服适配**：针对国服数据包与内容表（如 `LFGExtensionContent`）做映射，游戏版本更新后可通过校验脚本快速复核。

## 技术栈

- **服务端**：Rust（`warp` + `tracing`），MongoDB 存储
- **前端**：独立仓库的网页客户端
- **构建**：Cargo / rustup，CI 使用固定工具链

## 相关链接

- 项目仓库：[LittleNightmare/remote-party-finder](https://github.com/LittleNightmare/remote-party-finder/)
- 在线网站：[xivpf.littlenightmare.top](https://xivpf.littlenightmare.top/)
