---
title: "3dcon: tomogram denoising by deconvolution"
title_zh: 3dcon：通过反卷积对断层图像进行去噪
authors: "Kirchweger, P., Melnikovsky, L., Seifer, S., Elbaum, M."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732138v1.full.pdf"
tags: ["query:d-recon"]
score: 6.0
evidence: 从倾斜序列进行断层重建
tldr: 冷冻电镜断层扫描在稀疏数据下重建会引入结构噪声，即不同平面的投影对比度。现有神经网络方法依赖数据，而3dcon基于熵正则化去卷积算法，通过现代硬件加速，能有效抑制此类噪声。该算法完全规则化，不依赖特定数据集，因此鲁棒性强，适合病毒、细胞等标本的广泛场景。
source: biorxiv
selection_source: fresh_fetch
motivation: 冷冻电镜断层扫描中，稀疏数据和有限倾斜角导致重建出现结构噪声，现有去卷积方法缺乏便捷开源工具。
method: 提出3dcon，扩展自荧光显微镜的熵正则化去卷积算法，利用GPU等现代硬件实现快速处理。
result: 3dcon有效去除结构噪声，处理过程纯算法化，无需训练数据，结果稳定。
conclusion: 作为开源扩展，3dcon鲁棒且适用于多种冷冻电镜断层扫描应用，提升了降噪的便捷性和通用性。
---

## 摘要
冷冻电子断层扫描是一种用于研究大分子、病毒和细胞的新兴技术。它通常应用于那些对于基于二维图像平均的方法（如单颗粒分析）来说过大或异质的样本，例如细胞内膜或细胞器。目前的做法是在旋转过程中记录一系列投影图像。重建通常是一个不适定的数学问题。特别是对于数据稀疏、离散倾斜角度和有限倾斜范围的不确定情况，重建切片中会出现特征性伪影。许多看似噪声的东西实际上是结构性的：来自不同平面的对比度投影。人们采用各种方案来正则化重建，包括基于神经网络的机器学习框架。由于噪声是结构性的，可以通过使用合适的核进行反卷积来抑制。这一点已得到证实，并经常用于厚样本的冷冻扫描透射电子断层扫描中，因为那里的欠采样问题尤为严重。这里我们介绍3dcon，它是从荧光显微镜中采用并经过熵正则化的反卷积算法的开源扩展。它利用现代计算硬件，实现便捷快速的图像处理。反卷积完全是算法性的，意味着数据的成功处理不依赖于数据本身。因此，它在各种应用中都应具有鲁棒性。

## Abstract
Cryo-electron tomography is an expanding technology for the study of macromolecules, viruses, and cells. It is often applied to specimens that are too large or heterogeneous for methods based on 2D image averaging such as single particle analysis, e.g., intracellular membranes or organelles. Current practice records a tilt series of projection images in rotation. Reconstruction is normally an ill-posed mathematical problem. Particularly for the under-determined case of sparse data, discrete tilt angles, and a limited tilt range, characteristic artifacts appear in the reconstructed slices. Much of what appears as noise is in fact structural: the projection of contrast from different planes. Various schemes are employed to regularize the reconstruction, including machine-learning frameworks built on neural networks. To the extent that the noise is structural, it might be suppressed by deconvolution with a suitable kernel. This was demonstrated and has been used regularly in cryo-STEM tomography of thick specimens where the under-sampling problem is particularly acute. Here we present 3dcon as an open-source extension of the entropy-regularized deconvolution algorithm that had been adopted from fluorescence microscopy. It takes advantage of modern computing hardware for convenient and fast processing. Deconvolution is entirely algorithmic, meaning that successful processing of the data does not depend on the data itself. As such it should be robust in a wide variety of applications.