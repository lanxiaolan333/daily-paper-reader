---
title: Self-Calibrated Hyperspectral Neural Radiance Fields for 3D Reconstruction of Bone and Bone Analogues
title_zh: 用于骨骼及骨骼模拟物三维重建的自校准高光谱神经辐射场
authors: "Sigger, N., Nguyen, T. T., Ashraf, S., Tozzi, G."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732938v1.full.pdf"
tags: ["query:d-recon"]
score: 9.0
evidence: 高光谱神经辐射场用于三维重建
tldr: 高光谱成像可提供骨骼材料成分信息，但整合光谱与几何的3D重建常依赖外部位姿估计，限制了应用。本文提出BoNeRF-HS，一种自校准高光谱神经辐射场，无需COLMAP位姿，通过联合优化相机内参、体密度和高光谱辐射实现重建。门控光谱适配头有效建模波长相关辐射特征。在骨骼及类似物数据集上，该方法在重建质量和表面细节保留上优于现有方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有高光谱3D重建依赖外部位姿估计，难以有效融合光谱和几何信息。
method: 提出BoNeRF-HS，自校准神经辐射场，联合优化相机内参、密度和光谱辐射，并设计门控光谱适配头学习波长依赖特征。
result: 在多视图高光谱骨骼数据集上，BoNeRF-HS重建质量和表面细节保留优于现有方法。
conclusion: BoNeRF-HS无需外部位姿即可实现高质量的骨骼3D重建，提升了光谱建模能力。
---

## 摘要
高光谱成像（HSI）因能捕获与矿化组织相关的丰富波长依赖性信息，在骨骼评估中受到越来越多的关注。HSI提供与材料组成相关的详细光谱信息，而3D几何信息则支持表面形态和结构细节的分析。然而，集成光谱与几何信息仍然具有挑战性，特别是当传统重建流程依赖于外部位姿估计时。为解决这一难题，我们提出BoNeRF-HS——一种用于三维重建的自校准高光谱神经辐射场。BoNeRF-HS联合优化相机内参、体积密度和高光谱辐射，消除了对基于COLMAP位姿的需求。为改进光谱建模，我们引入了一个门控光谱适配头，学习波长相关的辐射特征以进行高光谱视图合成。我们在包含小鼠骨、小梁骨模拟物和皮质骨模拟物样本的多视角高光谱数据集上评估了BoNeRF-HS。实验结果表明，与现有方法相比，我们的框架实现了更优的重建质量，并更好地保留了骨骼表面细节。

## Abstract
Hyperspectral imaging (HSI) has gained increasing attention for bone assessment because it captures rich wavelength dependent information associated with mineralised tissue. HSI provides detailed spectral information related to material composition, while 3D geometric information supports the analysis of surface morphology and structural detail. However, integrating spectral and geometric information remains challenging, particularly when conventional reconstruction pipelines depend on external pose estimation. To address this challenge, we propose BoNeRF-HS, a self-calibrated hyperspectral neural radiance field for 3D reconstruction. BoNeRF-HS jointly optimises camera intrinsics, volume density, and hyperspectral radiance, removing the need for COLMAP based poses. To improve spectral modelling, we incorporate a gated spectral adapter head that learns wavelength dependent radiance features for hyperspectral view synthesis. We evaluate BoNeRF-HS on a multi-view hyperspectral dataset containing mouse bone, trabecular bone analogue, and cortical bone analogue samples. Experimental results demonstrate that our framework achieves improved reconstruction quality, and better preservation of bone surface details compared with existing approaches.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：BoNeRF-HS

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：高光谱成像（HSI）能捕获与骨骼材料组成相关的丰富波长信息，在骨科手术、法医学、生物力学中有重要应用。然而，现有高光谱三维重建方法通常需要外部相机位姿估计（如 COLMAP），这限制了其在无预先标定环境中的使用。
- **核心问题**：如何在不依赖外部位姿的前提下，同时重建三维几何与高光谱辐射？现有方法要么只做二维光谱分析，要么在三维重建中忽略光谱信息或需要繁琐的外部标定。
- **整体含义**：本文提出一种自校准高光谱神经辐射场 BoNeRF-HS，将相机内参、外参、体积密度和高光谱辐射联合优化，实现免位姿的 3D 重建，为手术导航、法医鉴定等提供非接触式的光谱-几何统一表示。

## 2. 方法论
### 2.1 核心思想
- 基于 NeRF–（自校准 RGB NeRF）扩展至高光谱域，将 RGB 预测头改为 B 波段光谱预测头。
- 引入**门控光谱适配头**（Gated Spectral Adapter Head），学习波长相关的残差校正，增强光谱建模能力。

### 2.2 关键技术细节
- **自校准相机参数**：将相机内参（fx, fy）和外参（旋转矩阵 R、平移向量 t）作为可学习参数，与神经辐射场一起优化。
- **光线生成与采样**：根据当前相机参数生成光线，沿光线采样 Ns=128 个点。
- **网络结构**：MLP 骨干（位置编码输入）→ 共享特征 h → 三个预测头：
  - 密度头：输出体密度 σ
  - 直接光谱头：输出初始光谱 Sdir ∈ ℝ^B（B=120 波段）
  - 门控光谱适配头：输出残差 ΔS ∈ ℝ^B 和门控值 g = sigmoid(·) ∈ (0,1)
  - **最终光谱**：Sfinal = Sdir + g · ΔS
- **高光谱体渲染**：采用 NeRF 的标准可微分体渲染，计算每个采样点的不透明度 α、累积透过率 T、渲染权重 w，最终沿光线积分得到渲染像素光谱。
- **损失函数**：光谱角映射器（SAM）损失，保留光谱形状相似性；可能还有光度损失（如 L2），文中明确使用了 SAM loss。

### 2.3 公式与算法流程（文字说明）
1. 输入：多视图高光谱图像 I_i ∈ ℝ^{H×W×B}（H=320, W=332, B=120）。
2. 初始化可学习相机内参 [fx, fy] 和外参 [R_i, t_i]。
3. 对于每个像素，生成光线 r(t) = o + td，采样 128 个 3D 点。
4. 将 3D 点与方向输入 MLP，获得特征 h。
5. 从 h 分别预测 σ、Sdir、ΔS 和 g。
6. 计算 Sfinal = Sdir + g·ΔS。
7. 使用体渲染合成该像素的 120 波段光谱。
8. 与真实光谱计算 SAM 损失，反向传播更新所有参数（包括相机参数、MLP 权重）。
9. 训练 10,000 个 epoch，每步随机采样 32×32 光线批次。

## 3. 实验设计
### 3.1 数据集
- 使用 NIREOS HERA VNIR 相机（400-1000 nm，120 光谱波段，空间分辨率 320×332）。
- 样本包括：
  - **小鼠骨**（后膝关节，剔除软组织后固定）
  - **小梁骨模拟物**（Sawbones 开孔 PCF15 聚氨酯泡沫，模拟松质骨）
  - **皮质骨模拟物**（Sawbones 闭孔 PCF40 聚氨酯泡沫，模拟密质骨）
- 每个样本采集 45 个视角（0-360°，步长 8°），经暗/白校正和背景去除。
- 训练/测试划分：约 90% 视图训练，剩余测试。

### 3.2 对比方法（baseline）
- **NeRF–**：扩展为高光谱输出（将 RGB 头替换为 B 波段头）
- **SiNeRF**：正弦神经辐射场，同样扩展为高光谱输出
- **NoPe-NeRF**：无位姿先验的神经辐射场，扩展为高光谱输出

### 3.3 评价指标
- **PSNR**（峰值信噪比）和 **SSIM**（结构相似性）衡量空间重建质量
- **RMSE**（均方根误差）衡量光谱精度

### 3.4 额外实验
- 在**小鼠软组织样本**上进行额外测试（表3）。
- 消融实验：不同适配头设计（表2）—— 直接光谱头、适配器无门、固定弱门、学习门。

## 4. 资源与算力
- **文中未明确说明 GPU 型号、数量或总训练时长。**
- 训练细节：PyTorch 实现，Adam 优化器，训练 10,000 个 epoch，每步随机采样 32×32 光线批次，沿光线采样 128 个点。
- 资源描述不足，无法判断算力需求规模。

## 5. 实验数量与充分性
- **实验数量**：共进行了三类主要实验：
  1. 3 个骨骼/模拟物样本上的定量比较（表1）及定性可视化（图1、图2）
  2. 消融实验（表2）对比 4 种适配头设计
  3. 额外软组织样本验证（表3、图3）
- **充分性评估**：
  - 覆盖了真实骨骼和两种典型骨模拟物，有一定代表性。
  - 对比了三种相关基线方法，且均进行了高光谱改造，确保了公平性。
  - 消融实验验证了门控适配头的有效性。
  - 但仅有 3 个主要样本，每个样本仅 45 个视图，数据集规模较小。未在真实手术场景或多物种骨骼上验证泛化性。
  - 未对比最新高光谱高斯泼溅（HyperGS）等方法（虽在引言中提及，但未纳入实验）。
  - 总体合理但范围有限。

## 6. 主要结论与发现
1. **BoNeRF-HS 在三个样本上均取得最佳 PSNR 和 SSIM**，同时 RMSE 最低或并列最低。
2. **自校准框架有效**：无需 COLMAP 位姿即可实现可靠的高光谱 3D 重建。
3. **门控光谱适配头带来显著提升**：学习门控残差校正优于直接光谱头和无门控变体。
4. **在软组织样本上也表现良好**，表明一定通用性。
5. 定性结果（误差热图、光谱曲线）显示 BoNeRF-HS 更好地保留了骨骼表面细节和光谱一致性。

## 7. 优点
- **创新性**：首次将自校准神经辐射场引入高光谱 3D 重建，解决了位姿依赖问题。
- **方法设计**：门控光谱适配头轻量且有效，能够学习波长相关残差，增强光谱建模。
- **实验严谨性**：对三种基线进行公平改造（均输出 B 波段光谱），消融实验设计清晰。
- **应用前景**：非接触、无辐射的手术导航、法医学、生物力学等领域有潜在价值。
- **开源性**：声明数据在合理请求下可获取，有利于复现。

## 8. 不足与局限
- **数据集规模有限**：仅 3 个样本、每个 45 视图，难以充分验证泛化性；缺乏多样性（仅小鼠骨+两种商业模拟物）。
- **未报告推理速度或实时性**：对于手术导航等实时应用缺乏性能评估。
- **未与最新高光谱 3D 方法（如 HyperGS、HS-3D-NeRF）直接比较**：文中虽引用但未进行实验对比。
- **算力需求不明确**：没有给出 GPU 型号、训练时间等关键资源信息，复现成本难以评估。
- **实验环境理想化**：固定光照、旋转台采集，与真实术中复杂光照和运动场景有差距。
- **门控适配头的泛化分析不足**：仅在骨骼/组织数据上测试，未在自然场景或其他材料上验证。
- **未讨论失败的极端情况**：如表面高度镜面反射、严重遮挡时的表现。

（完）
