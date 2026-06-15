<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-06-06 ~ 2026-06-15
- 运行时间：2026-06-15 14:37:03 UTC
- 运行状态：成功
- 本次总论文数：19
- 精读区：8
- 速读区：11

### 今日简报（AI）
本期日报共收录19篇论文，其中两篇高分工作分别用拉普拉斯增强和非线性加权损失（LEGS）以及NeRF渲染图像辅助3D高斯泼溅，推动了高质量3D重建。推荐优先关注这俩方向：前者在优化渲染质量上有突破，后者利用已有NeRF数据降低高斯泼溅训练成本。后续可试用其代码，并尝试验证LEGS的拉普拉斯先验是否适用于其他场景。
- 详情：[/20260606-20260615/README](/20260606-20260615/README)

### 精读区论文标签
1. [LEGS: Laplacian-Enhanced Gaussian Splatting with a Nonlinear Weighted Loss](/20260606-20260615/2606.07932v1-legs-laplacian-enhanced-gaussian-splatting-with-a-nonlinear-weighted-loss)  
   标签：评分：9.0/10、query:d-recon
   evidence：高斯溅射辐射场重建与新视图合成
2. [Leveraging NeRF-Rendered Images for 3D Gaussian Splatting](/20260606-20260615/2606.09034v1-leveraging-nerf-rendered-images-for-3d-gaussian-splatting)  
   标签：评分：9.0/10、query:d-recon
   evidence：利用NeRF渲染图像改进3D高斯泼溅的新视角合成
3. [Beyond Spherical Harmonics: Rethinking Appearance Models for Radiance Reconstruction](/20260606-20260615/2606.09794v1-beyond-spherical-harmonics-rethinking-appearance-models-for-radiance-reconstruction)  
   标签：评分：9.0/10、query:d-recon
   evidence：改进新视角合成和辐射重建中的视角相关外观模型
4. [Wild3R: Feed-Forward 3D Gaussian Splatting from Unconstrained Sparse Photo Collection](/20260606-20260615/2606.11894v1-wild3r-feed-forward-3d-gaussian-splatting-from-unconstrained-sparse-photo-collection)  
   标签：评分：9.0/10、query:d-recon
   evidence：使用3D高斯泼溅从稀疏照片集合进行前馈式3D重建
5. [Wild3R: Feed-Forward 3D Gaussian Splatting from Unconstrained Sparse Photo Collection](/20260606-20260615/2606.11894v2-wild3r-feed-forward-3d-gaussian-splatting-from-unconstrained-sparse-photo-collection)  
   标签：评分：9.0/10、query:d-recon
   evidence：使用3D高斯泼溅从稀疏照片集合进行前馈式3D重建
6. [Surflo: Consistent 3D Surface Flow Model with Global State](/20260606-20260615/2606.13644v1-surflo-consistent-3d-surface-flow-model-with-global-state)  
   标签：评分：9.0/10、query:d-recon
   evidence：通过流匹配从多个无位姿视图进行3D表面重建
7. [Flex4DHuman: Flexible Multi-view Video Diffusion for 4D Human Reconstruction](/20260606-20260615/2606.13655v1-flex4dhuman-flexible-multi-view-video-diffusion-for-4d-human-reconstruction)  
   标签：评分：9.0/10、query:d-recon
   evidence：从稀疏多视角视频通过扩散模型生成密集多视角视频用于4D人体重建
8. [Pano3D: Unified 3D Reconstruction and Panoptic Segmentation](/20260606-20260615/2606.14307v1-pano3d-unified-3d-reconstruction-and-panoptic-segmentation)  
   标签：评分：9.0/10、query:d-recon
   evidence：从图像进行统一3D重建和全景分割

### 速读区论文标签
1. [3D Oral Modelling with Improved Vertex Distribution Using Matching-Based Learning](/20260606-20260615/2606.07907v1-3d-oral-modelling-with-improved-vertex-distribution-using-matching-based-learning)  
   标签：评分：8.0/10、query:d-recon
   evidence：从多张口内图像进行深度学习的点云重建，并改进了顶点分布
2. [Empowering Feed-Forward Reconstruction Models with Metric Scale via Satellite Images](/20260606-20260615/2606.08205v1-empowering-feed-forward-reconstruction-models-with-metric-scale-via-satellite-images)  
   标签：评分：8.0/10、query:d-recon
   evidence：从图像进行前馈3D重建并消除尺度模糊
3. [TRON: Tracing Rays to Orchestrate a Neural Renderer for 3D Gaussian Reconstructions](/20260606-20260615/2606.11314v1-tron-tracing-rays-to-orchestrate-a-neural-renderer-for-3d-gaussian-reconstructions)  
   标签：评分：8.0/10、query:d-recon
   evidence：基于3D高斯的神经渲染，用于新视图合成与重光照
4. [DarkVGGT: Seeing Through Darkness Using Thermal Geometry without Daylight Tax](/20260606-20260615/2606.11326v1-darkvggt-seeing-through-darkness-using-thermal-geometry-without-daylight-tax)  
   标签：评分：8.0/10、query:d-recon
   evidence：低光环境下基于热成像的前馈3D重建
5. [DynaTok: Token-Based 4D Reconstruction from Partial Point Clouds](/20260606-20260615/2606.12189v1-dynatok-token-based-4d-reconstruction-from-partial-point-clouds)  
   标签：评分：8.0/10、query:d-recon
   evidence：基于标记的从部分点云进行4D重建
6. [Rethinking 3D Shape Generation: Diffusion over Superquadrics](/20260606-20260615/2606.08957v1-rethinking-3d-shape-generation-diffusion-over-superquadrics)  
   标签：评分：7.0/10、query:d-recon
   evidence：3D形状生成与超二次曲面，与点云重建方法相关
7. [3D-CoS: A New 3D Reconstruction Paradigm Based on VLM Code Synthesis](/20260606-20260615/2606.10478v1-3d-cos-a-new-3d-reconstruction-paradigm-based-on-vlm-code-synthesis)  
   标签：评分：7.0/10、query:d-recon
   evidence：提出基于VLM代码合成的新3D重建范式
8. [MoVerse: Real-Time Video World Modeling with Panoramic Gaussian Scaffold](/20260606-20260615/2606.13376v1-moverse-real-time-video-world-modeling-with-panoramic-gaussian-scaffold)  
   标签：评分：7.0/10、query:d-recon
   evidence：从单张图像实时构建3D高斯支架世界模型
9. [SceneConductor: 3D Scene Generation from Single Image with Multi-Agent Orchestration](/20260606-20260615/2606.08402v1-sceneconductor-3d-scene-generation-from-single-image-with-multi-agent-orchestration)  
   标签：评分：6.0/10、query:d-recon
   evidence：从单张图像生成3D场景，与从图像重建3D模型相关
10. [See More, Match Better: Multi-Source Feature Fusion for Two-View Correspondence Learning](/20260606-20260615/2606.09262v1-see-more-match-better-multi-source-feature-fusion-for-two-view-correspondence-learning)  
   标签：评分：6.0/10、query:d-recon
   evidence：多源特征融合用于两视图匹配，支持3D重建流程
11. [Latent Spatial Memory for Video World Models](/20260606-20260615/2606.09828v1-latent-spatial-memory-for-video-world-models)  
   标签：评分：6.0/10、query:d-recon
   evidence：用于视频世界模型新视角合成的潜在空间记忆


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
