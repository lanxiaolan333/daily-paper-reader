---
title: Fault-tolerant 3D reconstruction from 2D spatial proteomics sections
title_zh: 基于二维空间蛋白质组学切片的容错三维重建
authors: "Zhang, Z., Tan, Y., Nolan, G., Snyder, M., Ma, Z."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.733649v1.full.pdf"
tags: ["query:d-recon"]
score: 7.0
evidence: 从二维切片重建三维体积
tldr: 从稀疏2D组织切片重建3D分子体积受限于标记丢失和组织损伤。提出3D-Omics-Flow生成式流程，联合修复受损切片并以单细胞分辨率插值。在健康和疾病数据集上，将3D空间蛋白质组学扩展到实际采样方案。能从受损2D切片堆构建图集并支持下游分析。
source: biorxiv
selection_source: fresh_fetch
motivation: 重建3D分子体积受限于2D切片标记丢失和组织损伤，需要容错且能处理稀疏采样的方法。
method: 提出3D-Omics-Flow生成式流程，联合修复受损切片并实现单细胞分辨率的插值。
result: 在健康和疾病数据集上，3D-Omics-Flow成功将3D空间蛋白质组学扩展到实际采样方案。
conclusion: 能从受损2D切片堆构建3D分子图集，支持下游分析，拓展了空间蛋白质组学的应用。
---

## 摘要
从稀疏采样的二维组织切片重建三维分子体积受限于每个切片的标记丢失和组织损失。我们提出了3D-Omics-Flow，一个生成式流程，它能以单细胞分辨率联合修复受损切片并在切片之间进行插值。在涵盖健康和疾病的数据集中，3D-Omics-Flow将三维空间蛋白质组学扩展到实用的采样方案，从而能够从不完美的二维切片堆栈中构建图谱并进行下游分析。

## Abstract
Reconstructing 3D molecular volumes from sparsely sampled 2D tissue sections is limited by per-section marker dropout and tissue loss. We present 3D-Omics-Flow, a generative pipeline that jointly repairs damaged sections and interpolates between them at single-cell resolution. Across datasets spanning health and disease, 3D-Omics-Flow expands 3D spatial proteomics to practical sampling regimes, enabling atlas construction and downstream analysis from imperfect 2D section stacks.