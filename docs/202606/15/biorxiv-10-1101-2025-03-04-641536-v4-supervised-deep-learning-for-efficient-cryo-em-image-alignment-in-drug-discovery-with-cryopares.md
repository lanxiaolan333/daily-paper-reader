---
title: Supervised Deep Learning for Efficient Cryo-EM Image Alignment in Drug Discovery with cryoPARES
title_zh: 基于监督深度学习的cryoPARES方法：在药物发现中实现高效的冷冻电镜图像对齐
authors: "Sanchez-Garcia, R., Berndt, A., Apelbaum, A., Reeks, J., Williams, P. A., Poelking, C., Deane, C., Saur, M."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.03.04.641536v4.full.pdf"
tags: ["query:d-recon"]
score: 7.0
evidence: 基于深度学习的冷冻电镜图像3D重建
tldr: 冷冻电镜是药物发现中解析生物大分子结构的关键技术，但现有流程计算密集且需人工干预。cryoPARES提出一种基于预对齐数据集的深度学习姿态估计方法，快速准确预测粒子角度，并自动修剪粒子。该方法可实现单次通过实时重建，在七个配体结合复合物上验证，显著加速结构解析。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有冷冻电镜工作流程计算复杂且需人工干预，成为高通量药物发现瓶颈。
method: cryoPARES利用预对齐数据集训练深度学习模型，实现快速角度预测和自动粒子修剪。
result: 在七个配体结合复合物上快速确定结构，显著快于传统方法且无需人工干预。
conclusion: cryoPARES实现实时重建，为高通量结构药物发现提供高效自动化解决方案。
---

## 摘要
冷冻电镜（cryo-EM）是确定生物大分子三维结构的关键工具。当前的工作流程计算需求高且需要人工干预，这为基于结构的药物发现等高通量应用造成了瓶颈。在这种情境下，所有蛋白质样品在图像对齐相关分辨率下可以被认为是等效的，因此先前精修中关于粒子姿态的信息可以被复用。然而，现有方法忽略了这一先验知识，每个数据集都是从零开始对齐。我们提出cryoPARES，一种在预对齐数据集上训练的深度学习姿态估计方法。我们的方法不仅能够显著快于传统方法提供准确的角度预测，还引入了自动粒子修剪能力，消除了人工干预。结合其单次通过操作，这些特性实现了实时重构，从而在数据采集过程中提供反馈。我们通过对四个不同蛋白质靶标的七种配体结合复合物进行快速结构测定，展示了cryoPARES的有效性，并发布了三个新的片段结合冷冻电镜数据集。

## Abstract
Cryo-Electron Microscopy (cryo-EM) is a pivotal tool for determining 3D structures of biological macromolecules. Current workflows are computationally demanding and require manual intervention, creating bottlenecks for high-throughput applications like structure-based drug discovery. In such contexts, where all protein samples can be assumed to be equivalent at resolutions relevant for image alignment, information about particle poses from previous refinements could be reused. Existing methods, however, ignore this prior knowledge, aligning each dataset from scratch. We present cryoPARES, a deep learning pose estimation method trained on pre-aligned datasets. Our method not only provides accurate angular predictions significantly faster than traditional approaches but also introduces automated particle pruning capabilities that eliminate manual intervention. Together with its single-pass operation, these features enable real-time reconstructions that provide feedback during data acquisition. We demonstrate cryoPARESs effectiveness through rapid structural determination of seven ligand-bound complexes across four distinct protein targets and release three new fragment-bound cryo-EM datasets.