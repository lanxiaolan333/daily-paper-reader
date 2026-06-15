---
title: "ConnectoFM: A Foundation Model for Learning the Language of the Connectome"
title_zh: ConnectoFM：学习连接组语言的基础模型
authors: "Abir, A. R., Saha, A., Naswan, R., Bayzid, M. S."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.06.730367v1.full.pdf"
tags: ["query:d-recon"]
score: 6.0
evidence: 用于连接组学的EM图像重建，与从图像进行3D重建相关
tldr: "连接组学中EM图像数据规模巨大且异质性强，现有视觉模型未能针对连接组学领域优化膜边界和突触结构。ConnectoFM作为首个连接组学基础模型，在跨6个物种25个子域的170万无标签EM图像上预训练，结合掩码图像建模与对比对齐学习生物意义表示。利用冻结特征和轻量解码器迁移至二值分割、细胞分类和实例分割三大任务。在29个数据集上，仅用10%标注数据即超越使用100%数据的基线，尤其在膜、线粒体、囊泡、突触后致密区和突触上提升显著。该工作为神经回路精确重建提供了可泛化、数据高效的基础模型，并扩展至3D体积分割。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现代EM数据集规模巨大且异质，手动标注和模型重训练困难，现有基础模型未针对连接组学优化，难以保留膜边界和突触等关键结构。
method: 在跨6个物种25个子域的170万无标签EM图像上，结合掩码图像建模和对比对齐进行预训练，学习鲁棒生物表示；下游任务使用冻结特征加轻量解码器。
result: "在29个数据集上，仅用10%标注数据即超越使用100%数据的基线，尤其在膜、线粒体、突触等结构上表现突出，并成功扩展到3D分割。"
conclusion: ConnectoFM作为首个连接组学基础模型，实现了数据高效、泛化性强的神经回路重建，为可靠电路分析提供了可扩展方案。
---

## 摘要
从电子显微镜（EM）数据中准确重建神经回路是连接组学的核心任务，然而现代数据集规模庞大且异质性高，使得人工标注和针对特定数据集的模型重新训练成为重大挑战。尽管最近的EM基础模型提供了通用的视觉表示，但它们并非专门针对连接组学领域定制，而在该领域中，保留精细的膜边界和突触结构对于减少拓扑和连接错误至关重要。在此，我们提出ConnectoFM，这是首个连接组学基础模型，在来自六个物种和25个子领域的170万张未标记EM图像组成的多样化语料库上进行了预训练。ConnectoFM结合了掩码图像建模与对比对齐，直接从大规模连接组学数据中学习鲁棒的视觉表示。这些表示将EM图像按物种、脑区、发育队列和采集领域组织成具有生物学意义的聚类。通过使用冻结的预训练特征和轻量级解码头，我们将ConnectoFM迁移到三个重要的下游任务：二值分割、多类细胞分型和实例分割。在包括已建立基准的29个多样化数据集中，ConnectoFM始终优于现有的EM基础模型和需要从头开始训练特定任务的最新方法。仅使用10%的标注数据，ConnectoFM就超越了在100%标注预算下训练的基线模型，展示了ConnectoFM在低数据情况下的优越性。ConnectoFM的改进在具有挑战性和生物学重要性的目标上尤为显著，包括膜、线粒体、囊泡、突触后致密区和突触，并且在低标签设置下仍然强劲。扩展到3D体积分割和定性比较进一步表明，ConnectoFM在下游任务中实现了更准确且生物学上更忠实的结果。这些结果确立了ConnectoFM作为连接组学中通用且数据高效的基础模型，并为更可靠的神经回路重建提供了一条可扩展的途径。

## Abstract
Accurate reconstruction of neural circuits from electron microscopy (EM) data is central to connectomics, yet modern datasets are now so large and heterogeneous that manual annotation and dataset-specific model retraining have become major challenges. While recent EM foundation models provide general visual representations, they are not specifically tailored to the connectomics domain, where preserving fine membrane boundaries and synaptic structures is essential to mitigate topological and connectivity errors. Here, we present ConnectoFM, the first foundation model for connectomics, pretrained on a diverse corpus of 1.7 million unlabeled EM images drawn from six species and 25 subdomains. ConnectoFM combines masked image modeling with contrastive alignment to learn robust visual representations directly from large-scale connectomics data. These representations organize EM images into biologically meaningful clusters across species, brain regions, developmental cohorts, and acquisition domains. Using frozen pretrained features with lightweight decoder heads, we transfer ConnectoFM to three important downstream tasks: binary segmentation, multiclass cell typing, and instance segmentation. Across 29 diverse datasets, including established benchmarks, ConnectoFM consistently outperforms existing EM foundation models and state-of-the-art methods that require task-specific training from scratch. With only 10% labeled data, ConnectoFM surpasses the baselines trained on 100% annotation budget, showing the superiority of ConnectoFM in low-data regimes. Improvements of ConnectoFM are especially pronounced for challenging and biologically important targets, including membranes, mitochondria, vesicles, post-synaptic densities and synapses, and remain strong in low-label settings. Extension to 3D volumetric segmentation and qualitative comparisons further show that ConnectoFM enables more accurate and biologically faithful performance across downstream tasks. These results establish ConnectoFM as a generalizable and data-efficient foundation model for connectomics and provide a scalable route towards more reliable neural circuit reconstruction.