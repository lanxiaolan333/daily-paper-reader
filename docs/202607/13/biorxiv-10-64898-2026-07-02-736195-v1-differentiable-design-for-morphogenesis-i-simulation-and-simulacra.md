---
title: "Differentiable Design for Morphogenesis I: Simulation and Simulacra"
title_zh: 形态发生的可微分设计 I：模拟与拟像
authors: "Beker, O., Dumitrascu, B."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736195v1.full.pdf"
tags: ["query:d-recon"]
score: 6.0
evidence: 可微框架用于从静态体积重建3D形态发生
tldr: 细胞形态发生规则难以从稀疏观测推断。本文提出waxMorph，一个可微分的细胞框架，用于三维形态发生的生成与重建。在合成及生物数据上，它成功复现化学机械形状程序、从静态体积推断连续轨迹并恢复潜在信号。在心肌和肢体数据中，比传统插值更准确重建未观测中间态，并量化了形状组装复杂性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1704, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1663, \"height\": 2183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1677, \"height\": 1760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1726, \"height\": 1747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1725, \"height\": 2225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1723, \"height\": 1916, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1703, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1716, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1722, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1724, \"height\": 1773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1716, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736195-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1726, \"height\": 2275, \"label\": \"Table\"}]"
motivation: 细胞通过局部力与信息交换构建组织，观测稀疏导致规则难以推断。
method: 提出waxMorph，基于NVIDIA Warp的可微分细胞框架，融合物理与AI，GPU加速。
result: 在合成和生物数据中准确重建形态发生，比最优传输插值更优，区分发育轨迹。
conclusion: 提供开源混合框架用于学习局部相互作用生成生物形态。
---

## 摘要
细胞通过局部力量和信息的交换构建组织，然而支配这些相互作用的规则难以从稀疏的观测中推断。在这里，我们介绍waxMorph，一个基于细胞的可微分框架，用于生成和重建三维形态发生。在合成和生物学数据中，waxMorph重现了已建立的机械化学形态程序，从静态组织体积推断出连续轨迹，并恢复了空间组织的潜在信号。在一个发育中的小鼠心肌数据集上，它比最优输运插值更准确地重建了未观察到的中间几何形状，而在前肢中，它区分了相关的发育轨迹。通过改变细胞可获得的潜在线索的容量和空间组织，waxMorph还提供了一种基于模型的方法来量化形态组装的复杂性。waxMorph构建在NVIDIA Warp的空间计算生态系统内。它提供了一个开源、Python原生、GPU加速的混合物理-AI框架，用于学习局部细胞相互作用如何产生生物形态。

## Abstract
Cells build tissues through local exchanges of force and information, yet the rules governing these interactions are difficult to infer from sparse observations. Here, we introduce waxMorph, a differentiable cell-based framework for generating and reconstructing three-dimensional morphogenesis. In synthetic and biological data, waxMorph reproduced established mechanochemical shape programs, inferred continuous trajectories from static tissue volumes, and recovered spatially organized latent signals. In a developing mouse myocardium dataset, it reconstructed unobserved intermediate geometries more accurately than optimal-transport interpolation, while in forelimbs it distinguished related developmental trajectories. By varying the capacity and spatial organization of the latent cues available to cells, waxMorph also provides a model-based way to quantify the complexity of shape assembly. waxMorph is built within the spatial-computing ecosystem of NVIDIA Warp. It provides an open-source, Python-native, GPU-accelerated, hybrid physics-AI framework for learning how local cellular interactions give rise to biological form.