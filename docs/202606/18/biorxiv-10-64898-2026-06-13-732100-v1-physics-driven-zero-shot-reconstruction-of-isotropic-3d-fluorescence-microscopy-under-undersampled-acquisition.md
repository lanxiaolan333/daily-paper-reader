---
title: Physics-Driven Zero-Shot Reconstruction of Isotropic 3D Fluorescence Microscopy under Undersampled Acquisition
title_zh: 物理驱动的欠采样各向同性三维荧光显微镜零样本重建
authors: "Cao, R., Jin, T., Xin, F., Hou, Y., Fu, Y., Jin, B., Li, L., Gao, S., Wang, H., Li, Y., Saimi, D., Ren, W., Wang, W., Xin, G., Yuan, K., Chen, Z., Su, X., Kim, D., Li, M., Xi, P."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732100v1.full.pdf"
tags: ["query:d-recon"]
score: 7.0
evidence: 从低轴向采样率零样本重建各向同性3D显微图像
tldr: 荧光显微镜3D成像常因轴向欠采样导致分辨率各向异性。提出DeepUI零样本框架，利用物理引导退化机制，结合空间-频率联合学习生成缩放光学传递函数，并融合噪声退化与上采样分支。仅需5分钟训练，0.5分钟预测，实现各向同性重建，在散焦背景、噪声和分辨率模糊等挑战条件下表现优异。首次在低轴向采样率下实现各向同性3D荧光图像重建，无需训练数据。
source: biorxiv
selection_source: fresh_fetch
motivation: 常规轴向欠采样导致3D荧光显微镜分辨率各向异性，需实现各向同性重建以提升成像质量。
method: 提出DeepUI零样本框架，通过物理引导退化模拟轴向欠采样，采用空间-频率联合学习生成缩放OTF，包含噪声退化与上采样分支。
result: 在低轴向采样率下，DeepUI仅需5分钟训练即可快速预测，获得高质量各向同性结果，并有效应对散焦背景、噪声和模糊。
conclusion: DeepUI实现了零样本各向同性3D荧光重建，为轴向欠采样条件下的高分辨率成像提供了新范式。
---

## 摘要
三维成像是下一代荧光显微镜的发展方向。然而，常规的轴向降采样使得各向同性分辨率难以实现。在此，我们提出DeepUI，一个物理零样本框架，旨在从低轴向采样率中获取各向同性的三维荧光图像。DeepUI通过物理引导的退化过程充分利用三维图像的内在特征，结合空间-频率联合学习生成缩放的光学传递函数，并融合噪声退化和上采样分支。通常仅需5分钟训练和0.5分钟高通量快速预测，我们展示了DeepUI在获取各向同性结果方面的优越性能，以及对轴向降采样条件的独特性，甚至在更具挑战性的条件下（包括离焦背景、噪声和分辨率模糊）也表现优异。

## Abstract
Three-dimensional (3D) imaging represents the development of next generation of fluorescence microscopy. However, routine axial down-sampling makes isotropic resolution unrealistic. Here, we propose DeepUI, a physical zero-shot framework designed to achieve isotropic 3D fluorescence images from a low axial sampling rate. DeepUI fully leverages the intrinsic characteristics of 3D images through physics-guided degradation, which incorporates spatial-frequency joint learning to generate a scaled optical transfer function, combined with noise degradation and an up-sampling branch. Typically requiring just 5 minutes for training and 0.5 minutes for high-throughput and fast prediction, we demonstrate the superior performance of DeepUI to get isotropic results, and the exclusivity to axial down-sampling conditions, even in more challenging conditions, including defocused background, noise, and resolution blur.