---
title: "FEABAS: A Stitching and Alignment Tool for Serial EM Data"
title_zh: FEABAS：一种用于序列电子显微镜数据的拼接与对齐工具
authors: "Wu, Y., Lichtman, J. W."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730510v1.full.pdf"
tags: ["query:d-recon"]
score: 7.0
evidence: 拼接和对齐2D电子显微镜图像以重建3D体积，属于多图像三维重建
tldr: 体积电子显微镜重建神经回路面临图像伪影挑战，现有方法需人工编辑或高计算成本。FEABAS利用自适应网格与有限元方法弹性拼接对齐图像，高效处理皱褶、撕裂等伪影。该工具轻量级、跨平台开源，显著降低vEM应用门槛，提升大规模神经重建的自动化与精度。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有vEM重建方法对图像伪影鲁棒性差，依赖人工或深度学习，限制了技术推广。
method: FEABAS采用自适应网格建模与有限元方法，弹性形变拼接对齐序列图像，无需人工干预。
result: 该工具高效处理含皱褶、折叠、撕裂等伪影的切片数据集，重建精度与计算效率优于传统方法。
conclusion: FEABAS作为轻量开源工具，增强了vEM的普适性，为实现全脑连接组重建提供了实用解决方案。
---

## 摘要
体积电子显微镜（vEM）是重建神经系统突触级接线图的最先进且可扩展的技术。在图像采集之后，第一个关键步骤是重建数字化体积，即将数百万张电子显微镜图像组装成一个连贯的三维体积，这将支撑所有下游分析。现有方法在处理无伪影数据集时表现最佳，或者依赖于计算密集型深度学习方法或耗时的人工编辑，限制了vEM的更广泛应用。为了克服这些挑战，我们开发了FEABAS，这是一个可扩展、跨平台、开源软件包，旨在高效且精确地弹性拼接和对齐电子显微镜图像数据集。它利用自适应网格建模和有限元方法，能够稳健处理包含常见伪影（如皱纹、褶皱、撕裂和破损切片）的数据集，同时保持轻量级、易于实现的特性，适用于多种计算环境。

## Abstract
Volume electron microscopy (vEM) is the most advanced and scalable technique for reconstructing synaptic-level wiring diagrams of the nervous system. Following image acquisition, the first critical step is reconstruction of a digitized volume, which assembles millions of electron microscope images into a coherent 3D volume that will underpin all downstream analyses. Existing methods work best with artifact-free datasets or rely on computationally intensive deep learning approaches or time-consuming human editing, restricting the broader applicability of vEM. To circumvent these challenges, we have developed FEABAS, a scalable, cross-platform, open-source software package designed to elastically montage and align electron microscope image datasets with high efficiency and precision. It leverages adaptive mesh modeling and finite element methods, enabling robust handling of datasets containing common artifacts such as wrinkles, folds, tears, and broken sections, while maintaining a lightweight, accessible implementation suitable for diverse computational environments.