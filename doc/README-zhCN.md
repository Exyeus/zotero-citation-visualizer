# Zotero Citation Visualizer

[![zotero target version](https://img.shields.io/badge/Zotero-7-green?style=flat-square&logo=zotero&logoColor=CC2936)](https://www.zotero.org)
[![License](https://img.shields.io/badge/License-AGPL--3.0--or--later-blue?style=flat-square)](../LICENSE)

这是一个面向 Zotero 的引文关系可视化插件。

它的目标很明确：把某个 collection 中的论文转换成一张可交互的引文图谱。你既可以只查看本地馆藏中的引文关系，也可以结合 OpenAlex 在线补全，把库外论文也一起纳入图谱中，观察更大的引用网络。

[English](../README.md) | [简体中文](./README-zhCN.md)

## 功能亮点

- 直接从 Zotero 中为选定的 collection 生成引文图谱。
- 支持仅使用本地数据，或通过 OpenAlex 进行在线扩展。
- 可控制是否纳入库外论文，以及向外扩展的层数。
- 支持缩放、平移、重新加载、隐藏边和节点等交互操作。

## 快速预览

### 生成前配置

在生成窗口中可以指定 collection、是否启用在线补全、是否包含外部论文以及扩展深度。

![Citation Graph 配置窗口](./start_menu.png)

### 聚焦当前 collection 的图谱

当 `External Depth` 设为 `0` 时，图谱会更聚焦于当前 collection 内部的引用关系，适合快速查看馆藏内的结构。

![External Depth 为 0 的图谱](./graph_included_depth0.png)

### 扩展到库外论文

当启用在线补全并把 `External Depth` 设为 `1` 时，图谱会引入更多外部论文，用来展示更广的引用上下文。

![External Depth 为 1 的图谱](./graph_included_depth1.png)

## 使用方法

1. 在 Zotero 中选中一个 collection。
2. 从 collection 菜单，或 `Tools > Citation Graph (Selected Collection)` 打开插件。
3. 根据需要设置：
   - `Collection ID`
   - `Use Online Enrichment`
   - `Include External Papers`
   - `External Depth`
4. 点击 `Generate` 生成图谱。

## 图谱交互说明

- 蓝色节点表示当前选中 collection 中已有的条目；点击后会在 Zotero 中定位该条目。
- 橙色节点表示库外论文；点击后会打开其 DOI 页面或 OpenAlex 页面。
- 右键节点可以隐藏相关边、隐藏孤立节点，或重置隐藏状态。
- 可使用鼠标滚轮或触控板手势进行缩放与平移。

## 开发说明

- `npm install`
- `npm start`：本地开发与热重载
- `npm run build`：构建生产包并执行 TypeScript 检查

核心功能实现在 `src/modules/citationGraph.ts`。

## 致谢与许可

本项目基于 `windingwind/zotero-plugin-template` 搭建，但当前 README 已聚焦于本插件的引文图谱功能本身。

项目许可证为 `AGPL-3.0-or-later`。
