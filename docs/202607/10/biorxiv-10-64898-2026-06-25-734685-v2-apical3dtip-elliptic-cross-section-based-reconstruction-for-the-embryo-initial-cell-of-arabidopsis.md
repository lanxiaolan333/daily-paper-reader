---
title: "Apical3DTip: Elliptic Cross-section-based Reconstruction for the Embryo Initial Cell of Arabidopsis"
title_zh: Apical3DTip：基于椭圆截面的拟南芥胚胎初始细胞重建
authors: "Nonoyama, T., Kang, Z., Hanaki, Y., Itagaki, Y., Matsumoto, H., Kimata, Y., Tsugawa, S., Ueda, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734685v2.full.pdf"
tags: ["query:d-recon"]
score: 6.0
evidence: 从显微镜图像重建拟南芥胚胎细胞的三维结构
tldr: 针对拟南芥早期胚胎顶细胞，现有2D投影及网格重建方法难以定量分析动态三维形态，且需要大量手动校正。Apical3DTip通过坐标标准化（基于底平面和光轴）和椭圆拟合序列横截面，从活体成像中重建3D细胞，有效保留方向信息并降低噪声。该框架成功量化了顶细胞的形状各向异性，并追踪了分裂后子细胞体积，支持4D时序分析。实验验证了其可重复性和噪声鲁棒性。它提供了一个简单、无需网格的定量平台，为探索细胞几何与发育模式关系奠定基础。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1261, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1471, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1459, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1469, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 1186, \"label\": \"Figure\"}]"
motivation: 现有2D投影和网格重建方法难以定量分析拟南芥早期胚胎顶细胞的动态3D形态，且易丢失方向信息，需要大量手动校正。
method: 基于底平面和光轴标准化坐标系，对活体成像序列切片进行椭圆拟合，实现噪声抑制的3D细胞重构。
result: 成功量化顶细胞形状各向异性及子细胞体积变化，并验证了方法可重复性和噪声鲁棒性。
conclusion: 提供了简单、可重复的3D/4D细胞形态定量平台，克服了2D投影和网格依赖的局限性，适用于活体胚胎发育研究。
---

## 摘要
背景
细胞几何形状在拟南芥早期胚胎发生过程中决定分裂方向和体轴形成中起着核心作用。然而，由于活体成像研究通常依赖于二维（2D）投影，而现有的三维（3D）重建方法（包括基于网格的方法）常常丢失相对于胚珠的原始方向信息，并需要耗时的手动网格校正，因此对动态三维形态的定量分析仍然具有挑战性。此外，由于在液体培养基中漂浮和持续生长导致的胚胎位置波动，使得在共同坐标系中分析时间形态变化变得困难。

结果
我们开发了一个用于胚胎初始细胞（顶端细胞）形态定量三维和四维（4D；3D+时间）分析的稳健框架。该方法首先通过基于底面和观测光轴归一化细胞方向来建立标准化的3D坐标系。然后，通过对从堆叠成像数据中提取的连续截面进行基于椭圆的近似来重建细胞形态，从而无需复杂的表面网格重建即可实现精确的几何表征。为了评估形状各向异性，我们在3D中量化了顶端细胞形状。该框架进一步支持后续分裂的体积特征表征，为量化3D胚胎发生提供了基础。

结论
我们的框架为活体细胞形态的3D定量分析提供了一种简单且降噪的方法。我们将坐标归一化与基于椭圆截面重建的集成方法命名为Apical3DTip。该方法能够在无需大量手动校正的情况下实现细胞形状的一致比较。该方法克服了基于2D投影和网格依赖分析的关键局限性，并为在3D中定量细胞形状和子细胞形状提供了一个实用平台。更广泛地说，它为探索活体植物胚胎中细胞几何形状、形态动力学和发育模式之间的关系提供了定量基础。

## Abstract
BackgroundCell geometry plays a central role in determining division orientation and body axis formation during early embryogenesis in Arabidopsis thaliana. However, quantitative analysis of dynamic three-dimensional (3D) morphology remains challenging because live-imaging studies often rely on two-dimensional (2D) projections, while existing 3D reconstruction approaches, including mesh-based methods, often lose the original orientation information relative to the ovule and require labor-intensive mesh correction. In addition, embryo positional fluctuation caused by floating in liquid medium and continuous growth makes it difficult to analyze temporal morphological changes within a common coordinate system.

ResultsWe developed a robust framework for quantitative 3D and four-dimensional (4D; 3D + time) analysis of embryo initial cell (apical cell) morphology. The method first establishes a standardized 3D coordinate system by normalizing cell orientation based on the bottom plane and the optical axis of the observation. Cell morphology is then reconstructed through ellipse-based approximation of serial cross-sections extracted from stacked imaging data, enabling accurate geometric characterization without the need for complex surface mesh reconstruction. To evaluate shape anisotropy, we quantified the apical cell shape in 3D. The framework further supports the characterization of volumetric features of subsequent division, providing a basis for quantifying 3D embryogenesis.

ConclusionOur framework provides a simple and noise-reduced approach for quantitative analysis of living cell morphology in 3D. We named the integrated method of combining coordinate normalization with elliptical cross-section-based reconstruction Apical3DTip. This method enables consistent comparison of cell shapes without extensive manual corrections. The method overcomes key limitations of 2D projection-based and mesh-dependent analyses and offers a practical platform for quantifying cell shape and daughter cell shapes in 3D. More broadly, it provides a quantitative foundation for exploring the relationship between cell geometry, morphodynamics, and developmental patterning in living plant embryos.