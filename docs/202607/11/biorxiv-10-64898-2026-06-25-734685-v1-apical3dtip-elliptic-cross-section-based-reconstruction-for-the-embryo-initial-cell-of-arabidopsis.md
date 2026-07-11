---
title: "Apical3DTip: Elliptic Cross-section-based Reconstruction for the Embryo Initial Cell of Arabidopsis"
title_zh: Apical3DTip：基于椭圆截面的拟南芥胚胎初始细胞重建
authors: "Nonoyama, T., Kang, Z., Hanaki, Y., Itagaki, Y., Matsumoto, H., Kimata, Y., Tsugawa, S., Ueda, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734685v1.full.pdf"
tags: ["query:d-recon"]
score: 7.0
evidence: 从显微镜图像重建胚胎细胞的3D模型
tldr: 拟南芥胚胎早期顶细胞3D形态定量分析因活体成像依赖2D投影、现有3D重建丢失方位且需手动校正、胚胎浮动导致坐标系不一致而困难。Apical3DTip通过基于底面和观测光轴归一化建立标准化3D坐标系，并利用椭圆近似堆叠成像的连续横截面重建细胞几何，无需复杂网格。该方法成功量化了顶细胞3D形状各向异性，并支持后续分裂体积特征分析，有效降低了噪声。该框架克服了2D投影和网格依赖的局限，为探索植物胚胎细胞几何、形态动力学与发育模式的关系提供了定量平台。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1470, \"height\": 1267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1268, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-25-734685-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1468, \"height\": 426, \"label\": \"Figure\"}]"
motivation: 解决拟南芥胚胎顶细胞3D形态分析中2D投影和网格依赖方法的方位丢失与手动校正繁琐问题。
method: 通过底面与光轴归一化建立标准化3D坐标系，然后对堆叠成像的连续横截面进行椭圆近似重建细胞几何。
result: 成功量化顶细胞3D形状各向异性，并实现子细胞体积特征分析，无需复杂网格重建。
conclusion: Apical3DTip提供了一种简单降噪的活细胞3D形态定量方法，克服了传统2D与网格依赖局限。
---

## 摘要
背景在拟南芥早期胚胎发生过程中，细胞几何形状在决定分裂方向和体轴形成中起着核心作用。然而，动态三维形态的定量分析仍然具有挑战性，因为活体成像研究通常依赖于二维投影，而现有的三维重建方法（包括基于网格的方法）常常丢失相对于胚珠的原始方向信息，并且需要劳动密集型的网格校正。此外，由在液体培养基中漂浮和持续生长引起的胚胎位置波动使得在共同坐标系中分析时间形态变化变得困难。

结果我们开发了一个用于胚胎初始细胞（顶端细胞）形态定量三维和四维（3D+时间）分析的稳健框架。该方法首先通过基于底面和观察光轴归一化细胞方向来建立标准化的三维坐标系。然后，通过从堆叠成像数据中提取的连续截面的基于椭圆的近似来重建细胞形态，从而无需复杂的表面网格重建即可实现精确的几何表征。为了评估形状各向异性，我们在三维中量化了顶端细胞形状。该框架还支持后续分裂的体积特征的表征，为定量三维胚胎发生提供了基础。

结论我们的框架提供了一种简单且降噪的方法，用于三维活细胞形态的定量分析。我们将坐标归一化与基于椭圆截面的重建相结合的方法命名为Apical3DTip。该方法无需大量手动校正即可实现细胞形状的一致比较。该方法克服了基于二维投影和依赖网格的分析的关键局限性，并提供了一个实用平台，用于在三维中量化细胞形状和子细胞形状。更广泛地说，它为探索活体植物胚胎中细胞几何形状、形态动力学和发育模式之间的关系提供了定量基础。

## Abstract
BackgroundCell geometry plays a central role in determining division orientation and body axis formation during early embryogenesis in Arabidopsis thaliana. However, quantitative analysis of dynamic three-dimensional (3D) morphology remains challenging because live-imaging studies often rely on two-dimensional (2D) projections, while existing 3D reconstruction approaches, including mesh-based methods, often lose the original orientation information relative to the ovule and require labor-intensive mesh correction. In addition, embryo positional fluctuation caused by floating in liquid medium and continuous growth makes it difficult to analyze temporal morphological changes within a common coordinate system.

ResultsWe developed a robust framework for quantitative 3D and four-dimensional (4D; 3D + time) analysis of embryo initial cell (apical cell) morphology. The method first establishes a standardized 3D coordinate system by normalizing cell orientation based on the bottom plane and the optical axis of the observation. Cell morphology is then reconstructed through ellipse-based approximation of serial cross-sections extracted from stacked imaging data, enabling accurate geometric characterization without the need for complex surface mesh reconstruction. To evaluate shape anisotropy, we quantified the apical cell shape in 3D. The framework further supports the characterization of volumetric features of subsequent division, providing a basis for quantifying 3D embryogenesis.

ConclusionOur framework provides a simple and noise-reduced approach for quantitative analysis of living cell morphology in 3D. We named the integrated method of combining coordinate normalization with elliptical cross-section-based reconstruction Apical3DTip. This method enables consistent comparison of cell shapes without extensive manual corrections. The method overcomes key limitations of 2D projection-based and mesh-dependent analyses and offers a practical platform for quantifying cell shape and daughter cell shapes in 3D. More broadly, it provides a quantitative foundation for exploring the relationship between cell geometry, morphodynamics, and developmental patterning in living plant embryos.