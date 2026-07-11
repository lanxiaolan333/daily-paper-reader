---
title: "Differentiable Design for Morphogenesis I: Simulation and Simulacra"
title_zh: 可微分形态发生设计 I：模拟与拟像
authors: "Beker, O., Dumitrascu, B."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736195v2.full.pdf"
tags: ["query:d-recon"]
score: 6.0
evidence: 可微框架用于三维形态发生重建
tldr: 发育中细胞通过局部力与信息交换构建组织，但规则难以从稀疏观测推断。waxMorph提出可微细胞框架，基于NVIDIA Warp构建混合物理-AI系统。在合成与小鼠心肌、前肢数据中，该框架重现形态发生程序、推断连续轨迹，并量化形状组装复杂度。提供开源、GPU加速工具，用于学习局部细胞交互如何产生生物形态。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1704, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1663, \"height\": 2183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1677, \"height\": 1760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1726, \"height\": 1747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1725, \"height\": 2225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1723, \"height\": 1916, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1703, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1716, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1722, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1724, \"height\": 1773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1716, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736195-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1726, \"height\": 2275, \"label\": \"Table\"}]"
motivation: 细胞局部交互如何驱动形态发生尚不明确，现有方法从稀疏观测推断规则困难。
method: 提出waxMorph，基于可微细胞模型与NVIDIA Warp的GPU加速空间计算框架。
result: 在合成及小鼠心肌、前肢数据中，准确重建未观测中间形态并区分发育轨迹。
conclusion: waxMorph提供开源、GPU加速的混合物理-AI框架，可学习细胞局部交互如何构建生物形态。
---

## 摘要
细胞通过局部力和信息交换构建组织，但控制这些相互作用的规则难以从稀疏观测中推断。本文介绍了waxMorph，一个基于可微分细胞的框架，用于生成和重建三维形态发生。在合成和生物学数据中，waxMorph再现了已建立的机械化学形状程序，从静态组织体积推断连续轨迹，并恢复空间组织的潜在信号。在发育中的小鼠心肌数据集中，它比最优传输插值更准确地重建了未观测到的中间几何形状，在前肢中则区分了相关的发育轨迹。通过改变细胞可用的潜在线索的容量和空间组织，waxMorph还提供了一种基于模型的方法来量化形状组装的复杂性。waxMorph构建于NVIDIA Warp的空间计算生态系统之上，提供了一个开源、Python原生、GPU加速的混合物理-AI框架，用于学习局部细胞相互作用如何产生生物形态。

## Abstract
Cells build tissues through local exchanges of force and information, yet the rules governing these interactions are difficult to infer from sparse observations. Here, we introduce waxMorph, a differentiable cell-based framework for generating and reconstructing three-dimensional morphogenesis. In synthetic and biological data, waxMorph reproduced established mechanochemical shape programs, inferred continuous trajectories from static tissue volumes, and recovered spatially organized latent signals. In a developing mouse myocardium dataset, it reconstructed unobserved intermediate geometries more accurately than optimal-transport interpolation, while in forelimbs it distinguished related developmental trajectories. By varying the capacity and spatial organization of the latent cues available to cells, waxMorph also provides a model-based way to quantify the complexity of shape assembly. waxMorph is built within the spatial-computing ecosystem of NVIDIA Warp. It provides an open-source, Python-native, GPU-accelerated, hybrid physics-AI framework for learning how local cellular interactions give rise to biological form.