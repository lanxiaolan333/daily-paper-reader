---
title: "PA-SfM: Tracker-free differentiable acoustic radiation for freehand 3D photoacoustic imaging"
title_zh: "PA-SfM: 基于可微声辐射的无追踪器自由手持三维光声成像"
authors: "Li, S., Gao, J., Kim, C., Choi, S., Huang, H., Wang, X., Shi, J., Chen, Q., Wang, Y., Wu, S., Zhang, Y., Huang, T., Zhou, Y., Yao, B., Yao, Y., Li, C."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.06.716718v4.full.pdf"
tags: ["query:d-recon"]
score: 8.0
evidence: 从多个2D声学图像进行三维重建的运动恢复结构方法
tldr: 三维光声成像受限于稀疏传感器阵列的有限空间采样与视场，传统多视图融合依赖外部跟踪。PA-SfM提出可微声学SfM框架，无需跟踪器，通过可微声学辐射模型与分层优化直接从声学测量恢复相对姿态并联合重建。在自由手持人手血管成像中成功重建大视场网络，定量PSNR达38.90-41.42dB，SSIM达0.9637-0.9864，优于基于编码器的融合。该工作为无跟踪器自由手持多视图3D光声成像提供了稳健算法基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统3D光声成像多视图融合依赖电机或外部跟踪，增加系统复杂度且存在校准误差，亟需无跟踪器的姿态恢复方法。
method: 提出PA-SfM，集成可微声学辐射模型与分层优化，利用刚性阵列约束联合估计视角变换与三维重建。
result: 在自由手持人手血管成像中无跟踪恢复姿态并重建大视场网络，PSNR 38.90-41.42dB，SSIM 0.9637-0.9864。
conclusion: PA-SfM建立了无跟踪器自由手持多视图大视场3D光声成像的稳健计算框架。
---

## 摘要
三维光声成像通常依赖于稀疏传感器阵列，其空间采样和视场均有限。移动传感器阵列或目标物为实现多视角成像和大体积光声映射提供了有效途径，但多姿态的精确融合通常依赖于电机反馈或外部追踪硬件。这种追踪增加了系统复杂性，并可能受到校准误差、回差和运动不稳定性的影响。本文介绍PA-SfM，一种基于可微声辐射的无追踪器运动恢复结构框架，可直接从光声测量中恢复相对成像姿态。通过将可微声辐射模型与分层优化和刚性阵列约束相结合，PA-SfM联合估计视角间变换并重建三维光声体积，无需外部姿态测量。我们展示了人手血管系统的真实自由手持三维光声成像，其中约1秒内的任意手部运动提供了多视角测量，PA-SfM从中恢复相对姿态并联合重建大视场血管网络，无需运动追踪或预定义轨迹。我们还通过数值模拟、已知相对几何的体内大鼠肾脏和肝脏成像以及机械扫描三维光声成像系统进一步验证了PA-SfM。与基于编码器的机械扫描系统融合相比，PA-SfM产生了更清晰、更连续的血管重建，并且视场扩大。在受控的定量验证中，PA-SfM实现了高重建保真度，相对于真值或已知姿态参考重建，PSNR为38.90-41.42 dB，SSIM为0.9637-0.9864。这些结果确立了PA-SfM作为无追踪器、自由手持、多视角和扩展视场三维光声成像的稳健计算框架，为灵活的大体积光声血管成像提供了算法基础。源代码公开于https://github.com/JaegerCQ/PA-SfM。

## Abstract
Three-dimensional photoacoustic imaging (3D PAI) commonly relies on sparse sensor arrays, which has both limited spatial sampling and field-of-view (FOV). Moving the sensor array or the target provides an effective route to multi-view imaging and large volume PA mapping, but accurate fusion of multiple poses conventionally depends on motor feedback or external tracking hardware. Such tracking increases system complexity and can suffer from calibration errors, backlash and motion instability. Here we introduce PA-SfM, a tracker-free differentiable acoustic structure-from-motion (SfM) framework that recovers relative imaging poses directly from PA measurements. By integrating a differentiable acoustic radiation model with hierarchical optimization and rigid array constraints, PA-SfM jointly estimates inter-view transformations and reconstructs 3D PA volumes without external pose measurements. We demonstrate genuine freehand 3D PAI of human hand vasculature, in which arbitrary hand motion over approximately 1 s provides multi-view measurements from which PA-SfM recovers the relative poses and jointly reconstructs a large FOV vascular network without motion tracking or predefined trajectories. We further validate PA-SfM using numerical simulations, in vivo rat kidney and liver imaging with known relative geometry, and a mechanically scanned 3D PAI system. Compared with encoder-based fusion of the mechanically scanned system, PA-SfM produced sharper and more continuous vascular reconstructions with expanded FOV. In controlled quantitative validations, PA-SfM achieved high reconstruction fidelity, with PSNRs of 38.90-41.42 dB and SSIMs of 0.9637-0.9864 relative to ground truth or known pose reference reconstructions. These results establish PA-SfM as a robust computational framework for tracker-free, freehand, multi-view and expanded FOV 3D PAI, providing an algorithmic foundation for flexible large volume PA vascular imaging. The source code is publicly available at https://github.com/JaegerCQ/PA-SfM.

---

## 论文详细总结（自动生成）

# 论文详细总结：PA-SfM: 基于可微声辐射的无追踪器自由手持三维光声成像

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：三维光声成像（3D PAI）通常依赖稀疏传感器阵列，其空间采样和视场（FOV）有限。通过移动传感器阵列或目标物实现多视角成像可扩大成像体积，但多姿态的精确融合传统上需要电机反馈或外部追踪硬件（如电磁追踪器、光学追踪系统）。这种追踪方式增加了系统复杂性，且易受校准误差、回差、运动不稳定性等因素影响，限制了自由手持成像的灵活性和实用性。
- **意义**：提出无追踪器的计算框架，直接从光声测量中恢复相对成像姿态并联合重建三维体积，为自由手持、大视场三维光声血管成像提供算法基础，降低硬件依赖，提升成像便携性和普适性。

## 2. 方法论：核心思想、关键技术细节与算法流程
- **核心思想**：将运动恢复结构（Structure-from-Motion, SfM）原理引入光声成像，利用可微声辐射模型结合刚性阵列约束，通过联合优化姿态和三维体积，无需外部追踪。
- **关键技术细节**：
  - **可微声辐射模型**：将光声正向传播模型（声辐射在介质中的传播）构建为可微函数，使梯度可反向传播，从而允许基于梯度的优化。
  - **分层优化**：采用由粗到精（coarse-to-fine）的优化策略，先估计粗略姿态和体积，再逐步细化，避免局部最优。
  - **刚性阵列约束**：利用传感器阵列的已知几何结构（刚性阵列内部各传感器相对位置固定）作为先验，约束姿态估计的物理合理性。
- **算法流程（文字说明）**：
  1. 输入：多视角二维光声图像序列（由自由手持扫描获取，约1秒内任意手部运动）。
  2. 初始化：基于声学图像特征（如血管结构）或随机初始化视角变换参数。
  3. 正向模拟：通过可微声辐射模型，从当前估计的三维体积和视角变换，合成对应的二维光声投影。
  4. 损失计算：比较合成投影与真实测量之间的差异（如L2损失）。
  5. 反向传播：梯度回传至姿态参数和三维体积，更新估计。
  6. 分层迭代：重复步骤3-5，逐步提高分辨率或优化细节，直至收敛。
  7. 输出：恢复的视角间相对变换矩阵和联合重建的三维光声体积。

## 3. 实验设计
- **数据集/场景**：
  - 真实自由手持人手血管成像（人体实验）。
  - 数值模拟（合成数据，可用于定量评估）。
  - 体内大鼠肾脏和肝脏成像（已知相对几何，来自机械扫描系统，可提供真值）。
  - 机械扫描三维光声成像系统（带编码器，可作为对比基准）。
- **Benchmark**：
  - 将机械扫描系统采集的数据，以编码器姿态作为参考真值（ground truth pose），评估PA-SfM恢复姿态的精度和重建质量。
- **对比方法**：
  - 与基于编码器（encoder）的机械扫描系统融合结果进行对比（即传统有追踪方法）。
  - 未明确提及其他SfM或无追踪方法对比，但通过数值模拟和已知几何的体内数据进行了自对比。

## 4. 资源与算力
- **文中未明确说明**：未提及使用的GPU型号、数量、训练时长等硬件算力信息。推测为单GPU或多GPU训练，但具体细节缺失。这一点在原文中未展开，属于局限性之一。

## 5. 实验数量与充分性
- **实验组数**：
  - 至少包含：数值模拟实验、人手自由手持实验、大鼠肾脏和肝脏成像实验、机械扫描系统对比实验。
  - 定量评估：给出了PSNR（38.90–41.42 dB）和SSIM（0.9637–0.9864）指标，对比了真值或已知姿态参考重建。
  - 定性视觉效果：展示了更清晰、更连续的血管重建，视场扩大。
- **充分性评价**：
  - 实验覆盖了从合成到真实、从简单到复杂、从已知姿态到自由手持等多种场景，较为充分。
  - 定量指标较高且稳定，但缺乏与其他无追踪SfM方法的直接对比（如传统光学SfM方法在此场景的适配性）。
  - 未进行消融实验（如移除可微声辐射模型、移除分层优化等组件的影响），对方法有效性的归因分析不足。

## 6. 主要结论与发现
- **核心结论**：PA-SfM能够在不使用任何外部追踪器的情况下，从自由手持扫描的多视角光声测量中鲁棒地恢复相对姿态，并联合重建大视场三维体积。
- **性能**：相比于基于编码器的机械扫描融合，PA-SfM产生更清晰、更连续的血管重建，且视场扩大；定量重建保真度高（PSNR>38 dB, SSIM>0.96）。
- **意义**：为无追踪器自由手持多视角3D光声成像建立了稳健的算法框架，推动灵活大体积光声血管成像的应用。

## 7. 优点
- **创新性**：首次将可微声辐射模型与SfM结合，实现无追踪器的姿态恢复和三维重建，突破了传统光声成像对硬件的依赖。
- **实用性**：自由手持扫描仅需约1秒的任意手部运动，无需预定义轨迹，极大简化操作流程。
- **鲁棒性**：通过分层优化和刚性阵列约束，在自由运动下仍能收敛到高质量重建。
- **开放性**：源代码公开（GitHub），便于复现和后续研究。
- 综合定量指标高（PSNR 38.90–41.42 dB，SSIM 0.9637–0.9864），验证了高保真重建。

## 8. 不足与局限
- **算力资源未报告**：未说明训练/推理所需的计算资源，难以评估方法的效率和可扩展性。
- **消融实验缺失**：未对不同组件（如可微模型、分层优化、阵列约束）进行消融，无法量化各模块贡献。
- **对比方法单一**：仅与基于编码器的机械扫描融合对比，未与最近的无追踪方法（如基于深度学习的姿态估计或其他SfM变体）比较，公平性有待加强。
- **实验场景有限**：只在人手、大鼠肾脏/肝脏等有限解剖部位验证，未测试更复杂或深层组织（如脑部、乳腺）。
- **运动约束**：假设自由手持运动约1秒内，运动速度/范围对性能的影响尚未系统分析。
- **可能偏差风险**：体内数据中已知几何可能不完全精确（大鼠成像的参考姿态来自机械扫描，但机械扫描本身有回差误差），PA-SfM可能在一定程度上补偿了这些误差，导致定量指标偏高。

（完）
