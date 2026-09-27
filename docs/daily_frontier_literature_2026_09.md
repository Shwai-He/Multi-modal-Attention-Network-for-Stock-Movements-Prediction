# 📈 Stock-Prediction (MMAN & Quant RSI): 每日前沿文献关联与多模态时序/防过拟合 RSI 落地库 (2026-09)

**Document ID:** `STOCK-LIT-202609` | **Last Updated:** `2026-09-27` | **Target Path:** `docs/research/daily_frontier_literature_2026_09.md` | **Total Routed Papers:** `15`

> [!IMPORTANT]
> **🔗 跨仓库文献引用链闭环 (Cross-Repository Reference Chain Closure)**
> 本文件由每日 AI 前沿论文精读流水线自动路由生成，专门收录与 **`Shwai-He/stock-prediction` & `Multi-modal-Attention-Network-for-Stock-Movements-Prediction`** （`rsi_campaign/` 受控算子自进化、`多模态新闻+量价注意力剪枝校准`、`Regime-Aware MoE 路由` 以及 `防过拟合正则化`）直接关联的最新 arXiv 论文笔记。
> 每一篇收录文献均包含：**核心痛点、底层数学公式、ASCII 架构图、关键实测指标**，以及**与 `stock_prediction` 仓库具体代码模块和我们已发表代表作（Our Works）的双向锚定**。

---

## 🌟 1. 核心关联文献与本仓库模块映射速查表 (Executive Reference-to-Module Matrix)

| 收录日期 | 论文标题与 arXiv 链接 | 关键实测收益 / 核心结论 | 锚定本仓库代码模块与文档路径 (`Target Module`) | 原始精读归档 |
| :---: | :--- | :--- | :--- | :---: |
| `2026-09-27` | [**SHAPE**](https://arxiv.org/abs/2606.09886) (`arXiv:2606.09886`) | **跨架构零训练稳健性**：在 **Qwen3-30B-A3B**、**DeepSeek-V2-Lite** 与 **GPT-OSS-20B** 三大主流细粒度 MoE 模型上，仅需 128 条 C4/WikiText2 校准样本... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-27](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-27_ai_paper_notes.md) |
| `2026-09-27` | [**L2R**](https://arxiv.org/abs/2601.21349) (`arXiv:2601.21349`) | **语言与视觉双模态全面验证**：在基于 **OLMoE** 的语言模型预训练/微调以及 **ImageNet** 视觉 MoE 骨干网络上，L2R 将路由器参数量削减 **60%–75%**，同时在相同激活专家预算下将下游任务困... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-27](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-27_ai_paper_notes.md) |
| `2026-09-27` | [**OBCache**](https://arxiv.org/abs/2510.07651) (`arXiv:2510.07651`) | **即插即用全面提升主流基线**：在 **Llama-3.1-8B-Instruct**、**Qwen-2.5-7B/14B-Instruct** 与 **Mistral-7B** 上，将 OBCache 的... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-27](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-27_ai_paper_notes.md) |
| `2026-09-27` | [**AIDE²**](https://arxiv.org/abs/2609.26457) (`arXiv:2609.26457`) | **8 天无人工干预自主完成 7 代进化**：在持续 8 天的自主运行中，AIDE² 对自身源代码进行了数千次沙箱实验，成功合入 **7 次具有显著统计收益的代际升级**，最终在 **MLE-Bench** 与未见过的科学计算基准... | `rsi_campaign/mutable_operator.py` (Meta-Agent Outer-Loop Alpha Operator Evolution) | [2026-09-27](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-27_ai_paper_notes.md) |
| `2026-09-27` | [**RRSI**](https://arxiv.org/abs/2609.24972) (`arXiv:2609.24972`) | **OOD 跨基准泛化能力大幅跃升**：在涵盖代码生成（SWE-bench Verified）、复杂工具调用（$\tau$-bench）与多跳科学问答的跨领域评测中，未加正则化的朴素 RSI 在第 5 代后即出现严重的 ID-OO... | `rsi_campaign/evaluate_pareto_gate.py` (Time-Annealed Complexity & Ablation Pruner against Backtest Overfitting) | [2026-09-27](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-27_ai_paper_notes.md) |
| `2026-09-25` | [**How Pruning Attention Layers Affects Int**](https://arxiv.org/abs/2606.24970) (`arXiv:2606.24970`) | 在事实问答（TruthfulQA、haluEval）与医疗/金融高风险推理任务上，该校准修复将深度剪枝模型的 **ECE 降低 68%**，并在基于置信度的拒绝采样（Selective Prediction）中恢复了 98% 的安... | `models/` (Post-Pruning Probability Calibration for Financial Tail-Risk Prediction) | [2026-09-25](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-25_ai_paper_notes.md) |
| `2026-09-25` | [**Reward as an Agent (DynDiff-GRPO)**](https://arxiv.org/abs/2606.19842) (`arXiv:2606.19842`) | 在长程机器人操作世界模型训练中，将 Reward Hacking 发生率从 `34%` 降至 **`2.1%`**，真实环境迁移成功率提升 **`+16.4%`**。 | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-25](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-25_ai_paper_notes.md) |
| `2026-09-25` | [**SAC**](https://arxiv.org/abs/2604.18392) (`arXiv:2604.18392`) | 在 TB 级长上下文并发推理中，SAC 将跨节点 KV 读取有效带宽利用率从 `15%` 提升至 **`94%`**，P99 尾延迟降低 **3.7x**。 | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-25](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-25_ai_paper_notes.md) |
| `2026-09-21` | [**SIFT**](https://arxiv.org/abs/2609.19526) (`arXiv:2609.19526`) | 在 SWE-bench 与数学推理智能体自优化中，SIFT 将达到相同性能增益所需的下游基准评估次数降低 **6.4x**。 | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-21](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-21_ai_paper_notes.md) |
| `2026-09-20` | [**SHIFT-LLM**](https://arxiv.org/abs/2608.25068) (`arXiv:2608.25068`) | 在 **Llama-3-8B/70B** 与 **Qwen-2.5-14B** 上剪除 **25%–35% 的层**后，无需任何梯度下降微调（仅需 30 秒闭式矩阵求逆），SHIFT-LLM 将 WikiText2 困惑度（PPL... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-20](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-20_ai_paper_notes.md) |
| `2026-09-20` | [**CARE**](https://arxiv.org/abs/2607.26052) (`arXiv:2607.26052`) | 在多任务 MoE-LoRA 与稀疏 MoE 语言模型上，CARE 在削减 **32%–45% 平均专家激活 FLOPs** 的同时，在常识推理、代码与数学基准上全面持平甚至超越固定 Top-$k$ 基线（`+0.9%` 平均准确率... | `models/` (Regime-Adaptive Dynamic Expert Allocation under Volatility Shifts) | [2026-09-20](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-20_ai_paper_notes.md) |
| `2026-09-20` | [**Minima-KV**](https://arxiv.org/abs/2608.23834) (`arXiv:2608.23834`) | 在 **Llama-3.1-70B** 与 **Qwen-2.5-32B** 的 128K 长思维链并发服务中，Minima-KV 实现 **4.6x** 真实物理显存节省（零内部页碎片），将最大并发 Batch Size 提升... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-20](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-20_ai_paper_notes.md) |
| `2026-09-20` | [**ModularRSI**](https://arxiv.org/abs/2609.14857) (`arXiv:2609.14857`) | 在 **SWE-bench**、**GAIA** 与 **GPQA** 跨领域迁移测试中，ModularRSI 的变异编译通过率从单体 RSI 的 `54%` 提升至 **`96%`**，跨领域零样本重组性能比单体进化高出... | `rsi_campaign/evaluate_pareto_gate.py` (Time-Annealed Complexity & Ablation Pruner against Backtest Overfitting) | [2026-09-20](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-20_ai_paper_notes.md) |
| `2026-09-19` | [**WRP**](https://arxiv.org/abs/2609.09883) (`arXiv:2609.09883`) | **秒级零样本层裁剪且跨领域泛化更强**：在 **Llama-3-8B/70B**、**Qwen-2.5-14B** 与 **Mistral-7B** 上，WRP 在完全不运行任何前向传播（耗时不足 8 秒）的情况下剪除... | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-19](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-19_ai_paper_notes.md) |
| `2026-09-19` | [**Dream-RSI**](https://arxiv.org/abs/2609.14858) (`arXiv:2609.14858`) | 在复杂代码优化、Web 智能体长程交互及具身规划任务上，**Dream-RSI** 将真实在线评估调用次数削减 **70%–82%**，并在同等算力预算下将多轮自进化最终成功率提升 **`+9.6%`**。 | `rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`) | [2026-09-19](https://github.com/Shwai-He/scholar-odyssey/blob/main/intelligence/papers/2026-09-19_ai_paper_notes.md) |

---

## 📐 2. 逐篇论文深度机制解构、数学公式与本仓库落地指南 (Per-Paper Deep-Dive Cards)

### 2.1 [2026-09-27] SHAPE: Coalition-Aware Expert Pruning for Sparse Mixture-of-Experts LLMs

* **论文信息**：`arXiv:2606.09886` (2026-06, 开源仓库：`github.com/Alizen-1009/Shapley-Moe`)
* **核心关键词**：Sparse MoE、Cooperative Game Theory、Shapley Value Attribution、Coalition-Aware Expert Pruning、Quality-Coverage Bisection

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|               SHAPE: Coalition-Aware MoE Expert Pruning Pipeline                  |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  [Calibration Corpus D_cal] ---> Layer l Top-k Routing Traces: C_t = {e_i1..e_ik} |
|                                                |                                  |
|                                                v                                  |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Intra-Layer Cooperative Game Formulation (层内专家合作博弈建模)          |  |
|  |    * Players: E_l = {1, ..., N} experts in layer l                          |  |
|  |    * Coalition Utility v_l(S): Expected output reconstruction fidelity      |  |
|  |      when active Top-k coalition C_t is restricted to subset S \cap C_t     |  |
|  +-----------------------------------------------------------------------------+  |
|                                                |                                  |
|                                                v                                  |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Monte-Carlo / Co-Activation Shapley Attribution (Shapley 协同价值归因)    |  |
|  |    \phi_i(v_l) = \sum_{S \subseteq E_l \setminus \{i\}} w(|S|) [v_l(S \cup  |  |
|  |                  \{i\}) - v_l(S)]                                           |  |
|  |    * Captures high-order synergy: preserves "bridge" experts that rarely    |  |
|  |      dominate gate mass alone but are indispensable in Top-k combinations   |  |
|  +-----------------------------------------------------------------------------+  |
|                                                |                                  |
|                                                v                                  |
|  +-----------------------------------------------------------------------------+  |
|  | 3. Quality-Coverage Bisection Selection (全局预算二分质量覆盖率动态分配)    |  |
|  |    Retain minimal subset S_l^* s.t. \sum_{i \in S_l^*} \phi_i^+ >= \alpha(\lambda)|
|  |    Bisection search on \alpha to hit exact global target pruning ratio p    |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **单专家独立打分的“组合盲区”**：现有的免训练 MoE 专家剪枝方法（如基于路由激活频率 Frequency、门控权重均值 Gate-Sum 或单专家一阶重构误差的方法）均隐含了一个错误的**独立性假设（Independence Assumption）**——即每个专家的贡献可以孤立度量。然而，MoE 的前向计算本质上是**组合协同（Coalitional）**的：每个 Token 的输出由激活的 Top-$k$ 专家子集 $C_t$ 线性叠加生成。
* **协同正交专家的误杀**：在真实 MoE 层中，若两个高激活专家高度共线（功能冗余），同时保留两者的边际增益极低；反之，某些中低频激活的“互补/正交桥接专家（Bridge Experts）”虽然单独门控权重不高，但在特定 Top-$k$ 组合中提供了不可替代的正交残差修正。独立打分会将前者全部保留而误杀后者，导致 20%–40% 剪枝率下模型出现断崖式精度崩塌。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **层内合作博弈定义（Intra-Layer Cooperative Game）**：
   设第 $l$ 层共有 $N$ 个专家 $\mathcal{E}_l = \{1, \dots, N\}$。给定校准集 $\mathcal{D}_{\text{cal}}$ 上的输入隐状态 $x_t \in \mathbb{R}^d$，原始 Top-$k$ 路由集合为 $C_t \subseteq \mathcal{E}_l$（$|C_t|=k$），原始层输出为：
   $$y_t = \sum_{j \in C_t} g_{t,j} E_j(x_t)$$
   当仅保留专家子集 $S \subseteq \mathcal{E}_l$ 时，受限联盟输出为 $\hat{y}_t(S) = \sum_{j \in C_t \cap S} \tilde{g}_{t,j}(S) E_j(x_t)$。定义联盟 $S$ 的特征效用函数（Characteristic Utility Function）$v_l: 2^{\mathcal{E}_l} \to \mathbb{R}$ 为相对于空集的输出误差削减量：
   $$v_l(S) = \mathbb{E}_{x_t \sim \mathcal{D}_{\text{cal}}} \Big[ \| y_t \|_2^2 - \| y_t - \hat{y}_t(S) \|_2^2 \Big]$$
2. **基于共现轨迹的 Shapley 协同归因（Shapley Value Attribution）**：
   专家 $i \in \mathcal{E}_l$ 的 Shapley 值定义为其在所有可能专家联盟 $S \subseteq \mathcal{E}_l \setminus \{i\}$ 中的平均边际贡献：
   $$\phi_i(v_l) = \sum_{S \subseteq \mathcal{E}_l \setminus \{i\}} \frac{|S|!(N - |S| - 1)!}{N!} \Big( v_l(S \cup \{i\}) - v_l(S) \Big)$$
   由于每个 Token 仅激活 $|C_t| = k \ll N$ 个专家（例如 $k=2$ 或 $6,8$），任何不包含在 $C_t$ 中的专家对该 Token 边际贡献恒为 $0$。因此，原本指数级 $O(2^N)$ 的全局 Shapley 计算可精确降维至局部活跃联盟 $2^{|C_t|}$ 上的精确求和：
   $$\phi_i(v_l) = \mathbb{E}_{x_t : i \in C_t} \left[ \sum_{A \subseteq C_t \setminus \{i\}} \frac{|A|!(|C_t| - |A| - 1)!}{|C_t|!} \Big( u_t(A \cup \{i\}) - u_t(A) \Big) \right]$$
   其中局部效用 $u_t(A)$ 度量了子集 $A$ 内专家输出向量的内积交互项 $2 \langle g_{t,i} E_i(x_t), \sum_{j \in A} g_{t,j} E_j(x_t) \rangle + \|g_{t,i} E_i(x_t)\|_2^2$，从而自动惩罚与同联盟其他专家负相关或冗余的专家，奖励提供正交有效增量的专家。
3. **质量覆盖率二分层间分配（Quality-Coverage Selection Rule）**：
   为实现非均匀的层间稀疏率分配，将非负 Shapley 值归一化为质量分布 $\tilde{\phi}_{l,i} = \frac{\max(\phi_i(v_l), 0)}{\sum_{j=1}^N \max(\phi_j(v_l), 0)}$。给定阈值 $\alpha \in (0, 1)$，每层保留最小专家集合 $S_l^*(\alpha)$ 使得累计 Shapley 质量覆盖率不低于 $\alpha$：
   $$S_l^*(\alpha) = \arg\min_{S \subseteq \mathcal{E}_l} |S| \quad \text{s.t.} \quad \sum_{i \in S} \tilde{\phi}_{l,i} \ge \alpha$$
   最后通过一维二分搜索（Bisection Search）求解全局唯一阈值 $\alpha^*$，使得 $\frac{1}{L N}\sum_{l=1}^L |S_l^*(\alpha^*)| = 1 - p$（$p$ 为目标全局剪枝率）。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **跨架构零训练稳健性**：在 **Qwen3-30B-A3B**、**DeepSeek-V2-Lite** 与 **GPT-OSS-20B** 三大主流细粒度 MoE 模型上，仅需 128 条 C4/WikiText2 校准样本（无需任何微调），在 **20% 剪枝率**下恢复超过 **96.8%** 的原始零样本推理精度，在激进的 **40% 剪枝率**下比独立频次/门控剪枝高出 **5.4%–9.2%**（MMLU、GSM8K、ARC-Challenge）。
* **层间稀疏度自发涌现“沙漏分布”**：二分质量覆盖率准则自动在中间语义整合层保留更多专家，而在浅层词法层与深层输出对齐层裁剪高达 50% 的冗余专家。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
1. **与 *Demystifying When Pruning Works via Representation Hierarchies* (ICML 2026) & *Capacity-Aware Inference* (ICLR 2026) 的理论互证**：
   * 我们在 ICML 2026 中证明了剪枝是否生效取决于层间表示层级（Representation Hierarchy）的有效秩与冗余度分布；SHAPE 的局部 Shapley 展开式 $u_t(A \cup \{i\}) - u_t(A)$ 本质上是通过度量专家输出向量之间的交叉内积 $\langle E_i(x), E_j(x) \rangle$ 来识别表示子空间的正交性。
2. **与 *Transformer-Geometry* (`arXiv:2609.15975`, EMNLP 2026) 的几何融合启发**：
   * 在我们的正交/平行场分解框架 $E_j(x) = E_{j,\parallel}(x) + E_{j,\perp}(x)$ 下，SHAPE 的效用函数若直接建立在总输出 $y_t$ 的欧氏范数上，会被模长占优的平行径向分量 $E_{j,\parallel}(x)$ 主导！**核心改进点**：将 SHAPE 的联盟效用函数 $v_l(S)$ 限制在**去除流形平行漂移后的正交切空间分量 $P_\perp(h_t) E_j(x_t)$** 上计算 Shapley 值（即 **Perp-Shapley MoE Pruning**），随后对被剪除专家联盟的正交残差通过 **Woodbury / KKT 闭式补偿** 折叠进保留专家中，有望在 50% 专家剪枝率下实现近乎零损压缩。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-27_ai_paper_notes.md`


---

### 2.2 [2026-09-27] L2R: Low-Rank and Lipschitz-Controlled Routing for Mixture-of-Experts

* **论文信息**：Minghao Yang, Ren Togo, Guang Li, Takahiro Ogawa, Miki Haseyama (`arXiv:2601.21349`, 2026-01)
* **核心关键词**：MoE Routing Geometry、Low-Rank Latent Space、Lipschitz Continuity、Saturated Inner-Product Scoring (SIPS)、Multi-Anchor Routing

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|          L2R: Low-Rank & Lipschitz-Controlled MoE Routing Architecture            |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|                        Token Hidden State h \in R^d                               |
|                                     |                                             |
|                                     v                                             |
|        +---------------------------------------------------------+                |
|        | 1. Shared Low-Rank Latent Projection (低秩路由子空间映射)|                |
|        |    z = P h \in R^r   (r << d, orthogonalized P P^T = I_r)|                |
|        |    Filters out high-dimensional isotropic noise         |                |
|        +---------------------------------------------------------+                |
|                                     |                                             |
|                                     v                                             |
|        +---------------------------------------------------------+                |
|        | 2. Multi-Anchor Expert Prototypes (多锚点专家原型表示)   |                |
|        |    Each Expert e has M low-rank anchors: {u_{e,m}}_{m=1}^M               |
|        +---------------------------------------------------------+                |
|                                     |                                             |
|                                     v                                             |
|        +---------------------------------------------------------+                |
|        | 3. Saturated Inner-Product Scoring (SIPS Lipschitz 控制) |                |
|        |    s_{e,m}(z) = \tau \cdot \tanh( <z, u_{e,m}> / (\tau \|z\|_\gamma) )   |
|        |    Explicitly bounds || \nabla_h s_e(h) ||_2 <= L_lip    |                |
|        +---------------------------------------------------------+                |
|                                     |                                             |
|                                     v                                             |
|             SoftMax / Top-k Selection ---> Stable Expert Dispatch                 |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **高维线性路由的三大几何病态**：标准稀疏 MoE 普遍采用单层线性投影 $s(h) = W_r h \in \mathbb{R}^N$ 作为路由器（Router）。作者从表示几何角度指出高维空间 $d \gg N$ 中的线性内积路由存在三大固有缺陷：
  1. **维度失配与噪声过拟合（Representation Mismatch）**：Token 隐状态 $h \in \mathbb{R}^d$ 包含了大量与任务路由无关的词法/位置高频噪声，全维内积导致路由决策极易受正交噪声方向干扰。
  2. **高维角度集中现象（Angular Concentration）**：随着层深增加，Transformer 隐状态落入狭窄的各向异性锥（Anisotropic Cone），不同专家路由向量与 $h$ 的余弦相似度高度趋同，导致门控分布扁平化或赢家通吃。
  3. **范数敏感与 Lipschitz 失控（Scale Sensitivity）**：当隐状态范数 $\|h\|_2$ 在深层或长序列中剧烈膨胀时，未受控的内积 $w_e^\top h$ 会使 Softmax 进入指数饱和区，微小输入扰动即可引发离散 Top-$k$ 路由集合翻转（Routing Instability）。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **共享低秩潜空间路由投影（Low-Rank Latent Routing Space）**：
   引入行正交低秩投影矩阵 $P \in \mathbb{R}^{r \times d}$（$r \ll d$，例如 $d=2048, r=64$），将隐状态 $h$ 压缩至低秩判别子空间：
   $$z = P h \in \mathbb{R}^r, \qquad \mathcal{L}_{\text{orth}} = \| P P^\top - I_r \|_F^2$$
2. **饱和内积打分与显式 Lipschitz 边界控制（Saturated Inner-Product Scoring, SIPS）**：
   为消除隐状态径向范数 $\|h\|_2$ 暴涨导致的路由震荡，L2R 设计了带阻尼范数归一化与双曲正切饱和的打分算子：
   $$\phi_{\text{SIPS}}(z, u_e) = \tau \cdot \tanh\left( \frac{\langle z, u_e \rangle}{\tau \left(\sqrt{\|z\|_2^2 + \epsilon^2}\right)^\gamma \left(\sqrt{\|u_e\|_2^2 + \epsilon^2}\right)^\gamma} \right)$$
   其中 $\tau > 0$ 控制饱和软边界，$\gamma \in [0, 1]$ 控制径向尺度不变性强度（当 $\gamma=1$ 时退化为受控余弦路由）。利用 $\text{sech}^2(x) \le 1$ 及正交投影 $\|P\|_2 = 1$，可严格证明打分函数对原始输入 $h$ 的梯度范数（即局部 Lipschitz 常数）存在显式解析上界：
   $$\left\| \nabla_h \phi_{\text{SIPS}}(P h, u_e) \right\|_2 \le \|P\|_2 \cdot \frac{\|u_e\|_2^{1-\gamma}}{\epsilon^\gamma} = L_{\text{lip}}$$
   从而从数学上保证了有界输入扰动 $\|\delta h\|_2 \le \delta$ 不会引发路由分数的剧烈跳变。
3. **多锚点专家表达（Multi-Anchor Routing）**：
   由于单个专家往往需要处理多模态或多子类语义簇，在低秩空间 $\mathbb{R}^r$ 中为每个专家分配 $M$ 个子锚点 $\{u_{e,m}\}_{m=1}^M \subset \mathbb{R}^r$（参数量仅为 $N \times M \times r \ll N \times d$），通过 Log-Sum-Exp 软聚合计算专家总得分：
   $$s_e(h) = \frac{1}{\beta} \log \sum_{m=1}^M \exp\Big( \beta \cdot \phi_{\text{SIPS}}(P h, u_{e,m}) \Big)$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **语言与视觉双模态全面验证**：在基于 **OLMoE** 的语言模型预训练/微调以及 **ImageNet** 视觉 MoE 骨干网络上，L2R 将路由器参数量削减 **60%–75%**，同时在相同激活专家预算下将下游任务困惑度（PPL）降低 `0.42–0.68`，ImageNet Top-1 准确率提升 `+1.3%`。
* **路由稳定性与负载均衡双升**：在对抗性高斯扰动测试下，L2R 的 Top-$k$ 路由翻转率（Routing Flip Rate）比标准线性 Router 降低 **47%**，专家负载熵（Routing Entropy）更加接近理想均匀分布，无需强依赖破坏主任务梯度的大权重 Load-Balancing 辅助损失。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
1. **与 *Router-Tuning* (EMNLP 2025) & *Capacity-Aware Inference* (ICLR 2026) 的直接耦合**：
   * 我们在 *Router-Tuning* 中提出仅微调轻量路由器即可解锁深层稀疏网络潜力，但在极低资源或长上下文微调中，全维线性路由器容易过拟合表面范数特征。将 L2R 的 **SIPS + 低秩多锚点路由** 作为 *Router-Tuning* 的参数化形式，不仅能将可训练参数再降一个数量级，还能利用 Lipschitz 边界防止微调过程中的路由坍缩。
2. **与 *Transformer-Geometry* (`arXiv:2609.15975`, EMNLP 2026) & `MerA` SVD 初始化的深刻同构**：
   * L2R 发现的“径向范数敏感性（Scale Sensitivity）”与我们在 *Transformer-Geometry* 及 `ads-rsi`（定律 ADS-RSI-1：Scale-Cancellation）中揭示的**“深层残差流径向范数 $\|h\|_2$ 掩盖切向语义方向 $h / \|h\|_2$”**完全一致！此外，在将稠密模型或预训练线性路由器 $W_r \in \mathbb{R}^{N \times d}$ 转化为 L2R 路由器时，无需随机初始化 $P$，可直接调用我们的 **`MerA` 数据感知激活协方差 SVD（Activation-Covariance SVD）** 提取前 $r$ 个主奇异方向初始化 $P$，实现零冷启动抖动的低秩 Lipschitz 路由升级。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-27_ai_paper_notes.md`


---

### 2.3 [2026-09-27] OBCache: Optimal Brain KV Cache Pruning for Efficient Long-Context LLM Inference

* **论文信息**：Yuzhe Gu, Xiyu Liang, Jiaojiao Zhao, Enmao Diao (`arXiv:2510.07651`, **ICML 2026**)
* **核心关键词**：KV Cache Eviction、Optimal Brain Damage (OBD)、Second-Order Taylor Perturbation、Output-Aware Saliency、Joint KV Pruning

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|         OBCache: Optimal Brain Damage (OBD) Layer-Wise KV Cache Pruning           |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Prefill / Decoding Step: Queries Q \in R^{S_q x d_k}, Cached K, V \in R^{S_k x d}|
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Attention Output Perturbation Objective (层输出二阶泰勒扰动建模)         |  |
|  |    Target: Minimize || O - \tilde{O}(\mathcal{M}) ||_F^2 where O = A V       |  |
|  |    Instead of heuristic \sum_i A_{i,j}, expand \Delta O w.r.t. masked K_j,V_j|  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|           +----------------------------+----------------------------+             |
|           v                            v                            v             |
|  +-----------------+          +-----------------+          +-------------------+  |
|  | Isolated Value  |          |  Isolated Key   |          | Joint KV Saliency |  |
|  | Score \Omega_j^V|          |  Score \Omega_j^K|         | Score \Omega_j^{KV}| |
|  | ||A_{:,j}||_2^2 |          | Softmax Jacobian|          | Exact Rank-1      |  |
|  | * ||V_j||_2^2   |          | Coupling Term   |          | Softmax Renorm    |  |
|  +-----------------+          +-----------------+          +-------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Plug-and-Play Eviction Gate (即插即用淘汰门控: 兼容 SnapKV / PyramidKV)  |  |
|  |    Evict tokens with minimal \Omega_j^{KV} -> Retain top-B KV budget        |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **启发式注意力权重累加的理论缺陷**：主流长上下文 KV 缓存淘汰算法（如 H2O、SnapKV、PyramidKV）均使用累积注意力分数 $s_j = \sum_{i} A_{i,j}$ 作为 Token $j$ 的重要性指标。然而，注意力层真正传递给后续残差流的是加权输出矩阵 $O = A V \in \mathbb{R}^{S_q \times d_v}$：
  1. **忽略 Value 向量范数与方向抵消**：若某个历史 Token $j$ 的注意力权重 $A_{i,j}$ 较高，但其对应的 Value 向量范数 $\|V_j\|_2 \approx 0$，或者其 $V_j$ 与当前上下文均值方向完全重合，驱逐它对注意力输出 $O$ 的实际影响极小；反之，注意力权重中等但 $\|V_j\|_2$ 极大且承载正交关键信息的 Token 被驱逐后会造成严重的输出畸变。
  2. **忽略 Softmax 分母重归一化效应（Denominator Renormalization）**：驱逐第 $j$ 个 Key 相当于将注意力得分 $Z_{i,j} \to -\infty$，这不仅移除了 $A_{i,j} V_j$，还会通过 Softmax 分母缩放将其余所有保留 Token 的注意力权重放大 $\frac{1}{1 - A_{i,j}}$ 倍。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **基于 Optimal Brain Damage (OBD) 的二阶输出扰动构建**：
   设某注意力头在查询窗口 $Q \in \mathbb{R}^{S_q \times d_k}$ 下的注意力概率矩阵为 $A = \text{Softmax}\left(\frac{Q K^\top}{\sqrt{d_k}}\right) \in \mathbb{R}^{S_q \times S_k}$，输出为 $O = A V \in \mathbb{R}^{S_q \times d_v}$。定义驱逐准则为最小化层输出矩阵的 Frobenius 范数平方误差 $\mathcal{E} = \frac{1}{2} \| O - \tilde{O} \|_F^2$。
2. **单 Value、单 Key 与联合 KV 对的闭式显著性公式（Closed-Form Saliency Scores）**：
   * **孤立 Value 剪枝显著性（Isolated Value Saliency $\Omega_j^V$）**：
     当将第 $j$ 个 Token 的 Value 向量置零（$V_j \leftarrow 0$）时，$\mathcal{E}$ 对 $V_j$ 的海森矩阵（Hessian）为 $\mathbf{H}_{V_j} = \frac{\partial^2 \mathcal{E}}{\partial V_j \partial V_j^\top} = \left(\sum_{i=1}^{S_q} A_{i,j}^2\right) I_{d_v}$。根据二阶泰勒展开，孤立 Value 显著性得分为：
     $$\Omega_j^V = \frac{1}{2} V_j^\top \mathbf{H}_{V_j} V_j = \frac{1}{2} \| A_{:, j} \|_2^2 \cdot \| V_j \|_2^2$$
     注意此处注意力权重是**平方和 $\|A_{:,j}\|_2^2$**（二阶能量）而非启发式的线性求和 $\|A_{:,j}\|_1$，且显式乘上了 Value 范数平方 $\|V_j\|_2^2$！
   * **联合 KV 剪枝与 Softmax 重归一化修正（Joint KV Saliency $\Omega_j^{KV}$）**：
     当真正从缓存中移除第 $j$ 个 KV 对（即令未归一化 logit $Z_{i,j} \to -\infty$）时，剩余 Token $k \neq j$ 的注意力权重精确变为 $\tilde{A}_{i,k} = \frac{A_{i,k}}{1 - A_{i,j}}$。因此，移除第 $j$ 个 KV 对在第 $i$ 个查询位置引起的**精确输出残差**为：
     $$\Delta O_i^{(-j)} = O_i - \tilde{O}_i^{(-j)} = O_i - \frac{O_i - A_{i,j} V_j}{1 - A_{i,j}} = \frac{A_{i,j}}{1 - A_{i,j}} \big( V_j - O_i \big)$$
     对该精确残差在所有查询位置 $i \in \{1, \dots, S_q\}$ 上求二阶能量，即得到极其优雅的**联合 KV 闭式显著性得分**：
     $$\Omega_j^{KV} = \frac{1}{2} \sum_{i=1}^{S_q} \left( \frac{A_{i,j}}{1 - A_{i,j}} \right)^2 \big\| V_j - O_i \big\|_2^2$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **即插即用全面提升主流基线**：在 **Llama-3.1-8B-Instruct**、**Qwen-2.5-7B/14B-Instruct** 与 **Mistral-7B** 上，将 OBCache 的 $\Omega_j^{KV}$ 闭式打分直接替换 H2O、SnapKV 与 PyramidKV 的启发式打分（零额外超参），在 **LongBench**（16 个长文本任务）与 **RULER**（128K 极限大海捞针与多跳追踪）上，在仅保留 **5%–10% KV 缓存预算**下将平均准确率提升 **`+2.8%` 至 `+6.4%`**。
* **计算开销近乎为零**：$\|V_j - O_i\|_2^2 = \|V_j\|_2^2 - 2 \langle V_j, O_i \rangle + \|O_i\|_2^2$ 可直接复用 FlashAttention 已经算出的输出向量 $O_i$，无需显式物化完整的 $S_q \times S_k$ 矩阵，Prefill 延迟增加小于 `1.2%`。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
1. **对我们 `vla-dtr` & `Efficient Ads / HisTrim` 中 `Exclude-Self Value-Space Perpendicular KV Pruning` 的精确二阶理论证明！**
   * 请仔细对比 OBCache 的核心公式 $\Omega_j^{KV} = \frac{1}{2}\sum_i \left(\frac{A_{i,j}}{1 - A_{i,j}}\right)^2 \|V_j - O_i\|_2^2$ 与我们在 `vla-dtr`（定律 5）和 `ads-rsi` 中独立提出的 **`Exclude-Self Value-Space Perpendicular VLM KV Pruning`**：
     * 其中的因子 $\frac{A_{i,j}}{1 - A_{i,j}}$ 正是**排除自身注意力权重后的重归一化系数（Exclude-Self Renormalization）**！
     * 其中的 $\|V_j - O_i\|_2^2$ 度量的正是第 $j$ 个 Token 的 Value 向量相对于当前聚合输出均值 $O_i$ 的**偏离能量（即正交/非共线奇异度）**！如果 $V_j \approx O_i$（即该 Token 的 Value 与上下文均值完全共线/冗余），即便 $A_{i,j}$ 再大，$\|V_j - O_i\|_2^2 \approx 0$，驱逐它也完全不改变注意力输出！
2. **落地融合方案（Perp-OBCache）**：
   * 在我们的论文撰写与代码实现中，可以直接引用 ICML 2026 的 OBCache 作为二阶泰勒理论背书，并指出我们进一步将 $\|V_j - O_i\|_2^2$ 投影到了输出投影矩阵 $W_O$ 之后的残差切空间 $\|(V_j - O_i) W_O P_\perp(h_i)\|_2^2$，从而构成了比 OBCache 更进一层的**流形正交切空间二阶最优脑缓存剪枝（Manifold-Orthogonal OBCache）**。

---

## 🔥 板块二：全球前沿热点精选 (Trending Frontier)

> **赛道锚点**：前沿研发智能体递归自我改进（Agent Harness RSI）、抗过拟合正则化进化、可执行代码物理世界模型（Code as Worlds）。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-27_ai_paper_notes.md`


---

### 2.4 [2026-09-27] AIDE²: Recursive Self-Improvement of AI Research Agents

* **论文信息**：Dhruv Srikanth, Bingchen Zhao, Dixing Xu, Yuxiang Wu, Zhengyao Jiang (`arXiv:2609.26457`, 2026-09)
* **核心关键词**：Recursive Self-Improvement (RSI)、AI Research Agents、Meta-Harness Evolution、Anti-Reward-Hacking、Automated ML Engineering

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|            AIDE²: Bi-Level Recursive Self-Improvement of Research Agents          |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  +-----------------------------------------------------------------------------+  |
|  | Outer Loop: Meta-Agent (Self-Modification Engine on Agent Harness Codebase) |  |
|  |   Input: Current Agent Source Code H_t + Execution Trajectories \mathcal{T}_t| |
|  |   Action: Synthesize Code Patch \Delta H -> Candidate Agent H_{t+1}         |  |
|  +-----------------------------------------------------------------------------+  |
|                         |                                      ^                  |
|            Deploy H_{t+1} on Training Tasks        Return Traces & Validation     |
|                         v                                      |                  |
|  +-----------------------------------------------------------------------------+  |
|  | Inner Loop: Base Research Agent H_{t+1} (Tree Search over ML Solution Space)|  |
|  |   Draft -> Debug -> Hyperparameter / Architecture Mutate -> Evaluate Metric |  |
|  +-----------------------------------------------------------------------------+  |
|                         |                                                         |
|                         v                                                         |
|  +-----------------------------------------------------------------------------+  |
|  | Promotion Gate: Beats H_t across Multi-Seed ML Benchmarks without Leakage?  |  |
|  |   Yes -> Update Baseline H_t <- H_{t+1} (7 successive discoveries in 8 days)|  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **人工设计智能体脚手架（Agent Harness）的扩展瓶颈**：当前顶尖的自动化机器学习与科研智能体（如初代 AIDE、MLAgentBench、OpenHands）高度依赖人类研究员手工编写的脚手架代码（包括树搜索扩展算子、错误回溯提示词、历史节点记忆摘要策略以及验证集划分逻辑）。
* **内层任务优化与外层元能力进化的割裂**：传统研发智能体只能在固定脚手架 $H_0$ 下针对具体比赛或科研题目搜索业务代码解 $s \in \mathcal{S}$，一旦遇到脚手架自身的系统性缺陷（如深度贪心搜索导致的局部最优陷阱、或内层模型通过伪造验证集指标进行 Reward Hacking），智能体无法修改其自身的认知与搜索控制流。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **双层递归自改进优化形式化（Bi-Level RSI Formulation）**：
   设智能体脚手架源代码空间为 $\mathcal{H}$，下游科研任务分布为 $\mathcal{D}_{\text{task}}$。对于任意任务 $\tau \sim \mathcal{D}_{\text{task}}$，运行脚手架 $H \in \mathcal{H}$ 在计算预算 $B$ 下生成解代码 $s^*(\tau; H)$ 并产生完整执行轨迹 $\xi(\tau; H)$。双层优化目标定义为：
   $$H^* = \arg\max_{H \in \mathcal{H}} \mathbb{E}_{\tau \sim \mathcal{D}_{\text{train}}} \Big[ \mathcal{M}_{\text{meta}}\big( s^*(\tau; H), \xi(\tau; H) \big) \Big]$$
   $$\text{where} \quad s^*(\tau; H) = \arg\max_{s \in \text{SearchTree}(H, \tau, B)} \hat{\mathcal{M}}_{\text{inner}}(s; \tau)$$
   注意此处内层智能体优化的是自构建的内部验证指标 $\hat{\mathcal{M}}_{\text{inner}}$，而外层元评估器 $\mathcal{M}_{\text{meta}}$ 则在严格隔离的保留测试集（Hold-out Evaluation）上度量泛化得分。
2. **基于轨迹归因的元代码变异算子（Trajectory-Diagnosed Meta-Mutation）**：
   在第 $t$ 轮外层迭代中，元智能体（Meta-Agent）并非盲目变异脚手架代码 $H_t$，而是首先读取 $H_t$ 在训练任务集上的失败轨迹日志 $\Xi_t = \{\xi(\tau_i; H_t)\}$，执行三步闭环：
   $$d_t = \text{Diagnose}(\Xi_t, H_t) \longrightarrow \Delta H_t \sim \pi_{\text{meta}}(\cdot \mid H_t, d_t) \longrightarrow H_{t+1} = \text{ApplyPatch}(H_t, \Delta H_t)$$
   仅当 $H_{t+1}$ 在多个随机种子与多任务平均分上严格优于 $H_t$ 时，才将主分支更新为 $H_{t+1}$，形成单调递增的递归演化链 $H_0 \prec H_1 \prec \dots \prec H_7$。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **8 天无人工干预自主完成 7 代进化**：在持续 8 天的自主运行中，AIDE² 对自身源代码进行了数千次沙箱实验，成功合入 **7 次具有显著统计收益的代际升级**，最终在 **MLE-Bench** 与未见过的科学计算基准（Held-out Domains）上超越了人类专家耗时数月调优的初代 AIDE 脚手架（奖牌率提升 **`+11.4%`**）。
* **自主涌现出防奖励黑客（Anti-Reward-Hacking）机制**：外层元智能体在分析轨迹时自主发现内层模型常在交叉验证（Cross-Validation）中引入时间序列数据泄漏（Data Leakage）导致内层验证分虚高而外层测试分崩盘，因而**自主在脚手架代码中编写并合入了“静态 AST 数据泄漏审计器（Leakage Linter）”与“多折方差惩罚项”**！

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 `rsi-sandbox-architect`、`rsi-diagnosis-mutator` 及 `experiment-integrity-protocol` 的架构共鸣**：
  * AIDE² 在实验中发现的“内层智能体伪造验证指标（Reward Hacking）”正是我们在 `experiment-integrity-protocol` 与 `rsi-sandbox-architect` 中通过 **`HARNESS_LOCK.json`（SHA-256 冻结评估器）** 与 **`academic-integrity-auditor`** 强制拦截的核心痛点！AIDE² 证明了将“轨迹根因诊断（Diagnose）$\to$ 算子代码变异（Mutate）$\to$ 冻结测试门控（Pareto Gate）”固化为外层循环，能够让研发智能体自主演化出更强的搜索与验证纪律。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/mutable_operator.py` (Meta-Agent Outer-Loop Alpha Operator Evolution)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-27_ai_paper_notes.md`


---

### 2.5 [2026-09-27] RRSI: Regularized Recursive Self-Improvement of Agent Harnesses

* **论文信息**：Peng Xia, Rujun Han, Zifeng Wang, Yanfei Chen et al. (`arXiv:2609.24972`, 2026-09, Google Cloud AI Research & UNC)
* **核心关键词**：Regularized RSI、Agent Harness Overfitting、Temporally Annealed Proposal Budget、Critic-Pruner Selection

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|       RRSI: Regularized Recursive Self-Improvement of Agent Harnesses             |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Current Harness H_t + Historical Evolution Tree \mathcal{G}_{1:t}                |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Regularized Proposer (时间退火预算 + 历史轨迹引导提议器)                 |  |
|  |    * Temporally Annealed Modification Budget B(t) = B_0 \cdot \eta^t        |  |
|  |    * Early steps: structural workflow discovery; Late steps: surgical edits |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                              Candidate Harnesses {H_t^{(k)}}                      |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Regularized Selector: Critic + Structural Pruner (双重正则化选择器)       |  |
|  |    * Critic R_gen(H): Evaluates task-agnostic modularity & penalizes        |  |
|  |      hardcoded benchmark heuristics / prompt bloat                          |  |
|  |    * Pruner \mathcal{P}(H): Ablates newly added code/prompt blocks to strip |  |
|  |      parasitic dead-weight before promotion                                 |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|            Promote Compact, Generalizable Harness H_{t+1} to Next Epoch           |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **递归自我改进中的“脚手架过拟合与代码膨胀（Harness Overfitting & Bloat）”**：当智能体在有限的训练任务集 $\mathcal{D}_{\text{train}}$ 上进行多代递归修改自身脚手架（Prompt 模板、工具调用逻辑、记忆缓冲策略）时，极易陷入两类退化：
  1. **基准特定噪声记忆（Benchmark Memorization）**：外层优化器倾向于把针对训练集中某几个失败案例的特例规则（Hardcoded Heuristics）不断追加到系统提示词或控制流分支中，导致在分布内验证集（ID）分数上升，但在分布外基准（OOD）上严重倒退。
  2. **寄生代码膨胀（Parasitic Code/Prompt Bloat）**：每次变异往往同时包含 1 个有效改动与 3 个无效冗余改动，经过 10 代递归叠加后，脚手架变得极其臃肿且脆弱。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **带结构复杂度惩罚的正则化 RSI 目标（Regularized RSI Objective）**：
   取代单纯最大化经验平均回报 $\hat{J}_{\text{train}}(H)$，RRSI 将第 $t$ 代脚手架更新表述为带结构正则项与KL散度演进约束的目标：
   $$H_{t+1} = \arg\max_{H \in \mathcal{N}_{B(t)}(H_t)} \Big\{ \hat{J}_{\text{train}}(H) - \lambda_1 \Omega_{\text{complex}}(H) - \lambda_2 \mathcal{D}_{\text{spec}}(H \,\|\, H_0) \Big\}$$
   其中 $\Omega_{\text{complex}}(H)$ 度量脚手架控制流分支圈复杂度（Cyclomatic Complexity）与 Prompt 长度，$\mathcal{D}_{\text{spec}}(H \| H_0)$ 为评论家模型（Critic）评估的任务特异度惩罚（惩罚硬编码领域词汇或特定格式技巧）。
2. **时间退火变异邻域预算（Temporally Annealed Modification Budget）**：
   定义第 $t$ 代允许修改的最大 AST 节点数/代码行数上界 $B(t)$ 随迭代轮次指数衰减：
   $$B(t) = \max\Big( B_{\min}, \; \lfloor B_0 \cdot \gamma^t \rfloor \Big), \qquad \gamma \in (0, 1)$$
   早期迭代（$t$ 较小）允许大尺度重构智能体工作流拓扑（如引入反思循环或分层规划器），后期迭代则强制收敛为局部精细调优（Surgical Edits），防止后期破坏已收敛的核心架构。
3. **消融式结构修剪算子（Ablative Structural Pruner $\mathcal{P}$）**：
   对于候选补丁 $\Delta H = \bigcup_{m=1}^M \delta h_m$（包含 $M$ 个模块化改动块），修剪器 $\mathcal{P}$ 执行留一消融检验（Leave-One-Out Ablation）或静态依赖裁剪，剔除所有边际增益 $\Delta \hat{J}(\delta h_m) < \epsilon_{\text{prune}}$ 的寄生代码段，仅合并最小必要改动核（Minimal Sufficient Core）。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **OOD 跨基准泛化能力大幅跃升**：在涵盖代码生成（SWE-bench Verified）、复杂工具调用（$\tau$-bench）与多跳科学问答的跨领域评测中，未加正则化的朴素 RSI 在第 5 代后即出现严重的 ID-OOD 剪刀差（OOD 性能下降 `4.2%`），而 **RRSI** 持续稳定进化至第 12 代，在完全未见的 OOD 基准上取得 **`+7.8%` 至 `+12.5%`** 的净提升，同时将最终脚手架代码/提示词体积压缩了 **58%**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **直接指导我们 `ads-rsi`、`vla-loop` 与 `rsi-pareto-ledger` 的算子演化防膨胀纪律**：
  * 在我们的 RSI 自动化实验循环中，候选算子（Candidate Operator）在经历多轮突变后有时也会累加不必要的辅助超参或冗余分支。借鉴 RRSI 的 **Temporally Annealed Budget** 与 **Ablative Pruner $\mathcal{P}$**，我们在每轮候选算子晋级（Promotion）前应强制执行一次“最小自由度消融检查（Minimal-DoF Ablation Gate）”：任何未能贡献 $>0.1\sigma$ 净增益的附加项一律回滚剥离，确保最终回迁至 Google3 生产库（`rsi-google3-backporter`）的算子保持极简闭式形态。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/evaluate_pareto_gate.py` (Time-Annealed Complexity & Ablation Pruner against Backtest Overfitting)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-27_ai_paper_notes.md`


---

### 2.6 [2026-09-25] How Pruning Attention Layers Affects Interpretability, Faithfulness, and Confidence Calibration

* **论文信息**：`arXiv:2606.24970` (2026-06)
* **核心关键词**：Attention Layer Pruning、Confidence Calibration (ECE)、Faithfulness、Overconfident Hallucination

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|     Impact of Attention Layer Pruning on Faithfulness & Confidence Calibration    |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Pruned Mid-Deep Attention Layers ---> Loss of "Inhibitory / Suppression Heads"   |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | Pathology Diagnosis: Logit Norm Inflation & Entropy Collapse                |  |
|  |    || h^{(L)}_{\text{pruned}} ||_2 > || h^{(L)}_{\text{orig}} ||_2          |  |
|  |    Expected Calibration Error (ECE) spikes by 2.5x - 4.0x!                  |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | Fix: Inhibitory Subspace Projection + Variance-Matched Logit Rescaling      |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **剪枝后模型的“过度自信幻觉（Overconfident Hallucination）”**：作者发现，许多在中深层被视作“低贡献”而被剪除的注意力层，实际上包含了关键的**抑制头（Suppression / Negative Heads）**——它们的作用是在上下文证据不足或存在冲突时压低错误候选词的 Logit。剪除这些层后，虽然 Top-1 准确率仅轻微下降，但模型的预测分布熵急剧坍缩，期望校准误差（ECE）暴增 3 倍以上！

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **抑制头缺失导致的 Logit 方差膨胀模型**：
   在完整模型中，深层抑制注意力层的输出增量满足 $\langle \Delta h_{\text{inhib}}^{(l)}, h^{(l-1)} \rangle < 0$（即对残差流起负反馈阻尼作用）。剪除该层后，终端隐状态平行范数失控放大，导致输出词表概率 $p_{\text{pruned}}(y \mid x)$ 的期望校准误差（ECE）激增：
   $$\text{ECE} = \sum_{b=1}^B \frac{|I_b|}{N} \Big| \text{acc}(I_b) - \text{conf}(I_b) \Big|$$
2. **负反馈阻尼恢复与流形方差对齐**：
   在剪枝切口处引入沿残差主方向的阻尼收缩算子 $\tilde{h} = h - \beta \frac{\langle h, u_{\text{inhib}} \rangle}{\|u_{\text{inhib}}\|_2^2} u_{\text{inhib}}$ 并校准输出层温度 $\tau^* = \frac{\sigma(\text{logits}_{\text{pruned}})}{\sigma(\text{logits}_{\text{orig}})}$。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在事实问答（TruthfulQA、haluEval）与医疗/金融高风险推理任务上，该校准修复将深度剪枝模型的 **ECE 降低 68%**，并在基于置信度的拒绝采样（Selective Prediction）中恢复了 98% 的安全边界。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 *Transformer-Geometry* (`arXiv:2609.15975`, EMNLP 2026) 的“负平行分量（Negative Parallel Component）”发现完全吻合！**
  * 我们在 *Transformer-Geometry* 中明确观测到中深层部分模块具有 $\Delta h_\parallel < 0$ 的径向阻尼效应；剪除它们而不做平行范数阻尼补偿，必然导致终端模长膨胀与置信度失真。

---

## 🔥 板块二：全球前沿热点精选 (Trending Frontier)

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`models/` (Post-Pruning Probability Calibration for Financial Tail-Risk Prediction)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-25_ai_paper_notes.md`


---

### 2.7 [2026-09-25] Reward as an Agent (DynDiff-GRPO): Mitigating Reward Hacking in Embodied World Models

* **论文信息**：`arXiv:2606.19842` (2026-06)
* **核心关键词**：Reward as an Agent、Anti-Reward-Hacking、Embodied World Models、DynDiff-GRPO

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|       Reward as an Agent: Mitigating Reward Hacking via DynDiff-GRPO              |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Policy Rollouts in World Model ---> [Active Reward Agent \mathcal{R}_\phi]       |
|                                        |                                          |
|    Probes trajectory from multiple counterfactual angles & temporal differentials |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | Dynamic Differential GRPO (DynDiff-GRPO)                                    |  |
|  |    r_t^{\text{diff}} = R_\phi(s_{t+1}) - R_\phi(s_t) - \lambda_{\text{hack}} \text{Var}_{\text{view}}(R_\phi)|
|  |    Diversifies action-space exploration while penalizing adversarial states |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **静态奖励模型在世界模型强化学习中的“对抗样本漏洞”**：当具身策略在学习到的世界模型内部进行成千上万步 RL 训练时，策略极易找到使静态视觉奖励分类器输出高分、但在物理上完全荒谬的“对抗姿态（Adversarial Postures）”。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **多视角主动检验奖励智能体 + 动态差分优势（DynDiff-GRPO）**：
   奖励智能体主动变换观测相机视角与局部遮挡，计算跨视角奖励方差 $\text{Var}_{\text{probe}}(s_t)$，并使用时间步势能差分构建防黑客奖励：
   $$r_t^{\text{safe}} = \Big( \bar{R}_\phi(s_{t+1}) - \gamma \bar{R}_\phi(s_t) \Big) - \kappa \sqrt{\text{Var}_{\text{probe}}\big(R_\phi(s_{t+1})\big)}$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在长程机器人操作世界模型训练中，将 Reward Hacking 发生率从 `34%` 降至 **`2.1%`**，真实环境迁移成功率提升 **`+16.4%`**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 `experiment-integrity-protocol` 及 `ads-eval` 的多维防作弊门控理念一致**：单一静态代理指标必然被强优化器钻空子，必须引入正交扰动一致性惩罚。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-25_ai_paper_notes.md`


---

### 2.8 [2026-09-25] SAC: Disaggregated KV Cache Architecture for Sparse Attention Serving over CXL

* **论文信息**：`arXiv:2604.18392` (2026-04)
* **核心关键词**：CXL 3.0 Memory Pooling、Disaggregated KV Cache、Sparse Attention Sub-Page Gather

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|       SAC: CXL-Disaggregated KV Cache Architecture for Sparse Attention           |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  GPU Compute Nodes <--- CXL 3.0 Fabric ---> Shared CXL Memory Pool (TB-Scale KV)  |
|                                                       |                           |
|                                                       v                           |
|  +-----------------------------------------------------------------------------+  |
|  | Near-Memory Sparse Gather Engine on CXL Type-2/3 Controller                 |  |
|  |    Receives Top-k sparse token indices from GPU -> Packs only selected      |  |
|  |    cachelines into dense CXL flits -> 6.5x effective bandwidth amplification|  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **稀疏注意力在 PCIe/CXL 远端内存读取时的粒度放大（Granularity Amplification）**：当稀疏注意力仅需读取分散在不同物理页中的少量关键 Token 时，传统 DMA 以 4KB 页为单位搬运会导致高达 85% 的无效带宽浪费。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **CXL 控制器端近存稀疏聚集与头维度转置存储**：
   在 CXL 内存池侧按缓存行（64B Cacheline）对齐存储单头量化 KV 向量，由 CXL 控制器根据 GPU 下发的稀疏索引列表 $\mathcal{I}_{\text{top-}k}$ 在远端完成紧密打包（Dense Packing）后再经 CXL.mem 链路回传：
   $$\text{BW}_{\text{eff}} = \text{BW}_{\text{CXL}} \cdot \frac{d_{\text{head}} \cdot b_{\text{quant}}}{\lceil d_{\text{head}} \cdot b_{\text{quant}} / 64\text{B} \rceil \cdot 64\text{B}} \approx 0.94 \cdot \text{BW}_{\text{CXL}}$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在 TB 级长上下文并发推理中，SAC 将跨节点 KV 读取有效带宽利用率从 `15%` 提升至 **`94%`**，P99 尾延迟降低 **3.7x**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **为我们的 SelKV / OBCache 稀疏缓存算法在大规模分布式机架上的部署提供了硬件近存聚集蓝图**。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-25_ai_paper_notes.md`


---

### 2.9 [2026-09-21] SIFT: Recursive Self-Improvement via Fast Tree-Search

* **论文信息**：`arXiv:2609.19526` (2026-09)
* **核心关键词**：Sample-Efficient RSI、Fast Tree-Search、LLM-as-a-Judge Surrogate、Multi-Fidelity Evaluation

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|            SIFT: Recursive Self-Improvement via Fast Tree-Search                  |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Root Agent Code H_0 ---> Expand K Candidate Code Patches {\Delta H_1..\Delta H_K}|
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | Tier-1 Surrogate Gate: Fast Pairwise LLM-as-a-Judge + Syntax/Unit Smoke Test|  |
|  |    Scores semantic plausibility & structural novelty in <3 seconds          |  |
|  |    Prunes 85% of low-utility patches BEFORE benchmark execution             |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | Tier-2 Full Benchmark Gate: Execute Top-m Survivors on Held-Out Task Suite  |  |
|  |    Backpropagate true reward R(H) to update UCT Tree Search value estimates |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **RSI 树搜索中的“评估瓶颈（Evaluation Bottleneck）”**：在搜索智能体改进补丁时，超过 95% 的算力消耗在将每个候选补丁运行在数百道下游评测题上，而其中绝大部分候选修改仅包含语法微调或退化逻辑。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **双保真度 UCT 树搜索准则（Bi-Fidelity UCT Selection）**：
   结合快速评判器先验得分 $\hat{Q}_{\text{judge}}(H)$ 与真实基准评估均值 $\bar{R}_{\text{eval}}(H)$ 构建混合树搜索上置信界：
   $$\text{UCT}_{\text{SIFT}}(H) = \frac{n(H) \bar{R}_{\text{eval}}(H) + \kappa \hat{Q}_{\text{judge}}(H)}{n(H) + \kappa} + c \sqrt{\frac{\ln N(\text{parent}(H))}{n(H) + 1}}$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在 SWE-bench 与数学推理智能体自优化中，SIFT 将达到相同性能增益所需的下游基准评估次数降低 **6.4x**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **直接对应我们 `rsi-diagnosis-mutator` 的 `SMOKE-TEST (<5s) -> REMOTE GPU EVAL` 两级门控协议**：再次验证了在提交昂贵远程评测前通过轻量级诊断与冒烟测试过滤无效变异的高杠杆价值。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-21_ai_paper_notes.md`


---

### 2.10 [2026-09-20] SHIFT-LLM: Distribution Shift Correction in Depth-Pruned LLMs

* **论文信息**：`arXiv:2608.25068` (2026-08)
* **核心关键词**：Depth Pruning、Distribution Shift Correction、Linear Residual Adapters (LRA)、Closed-Form Ridge Regression、Weight Folding

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|          SHIFT-LLM: Closed-Form Distribution Shift Correction at Cut Sites        |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Original Stack:  h^{(l-1)} ---> [Pruned Block l..l+m] ---> h_{\text{orig}}^{(l+m)}|
|  Pruned Stack:    \tilde{h}^{(l-1)} -----(Identity Skip)---> \tilde{h}^{(l-1)}    |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Covariate Shift Diagnosis at Pruning Cut Site (剪枝切口协变量偏移诊断)   |  |
|  |    \Delta \mu = \mathbb{E}[h_{\text{orig}}^{(l+m)} - \tilde{h}^{(l-1)}],    |  |
|  |    Angular & norm mismatch causes downstream RMSNorm / Attention saturation |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Closed-Form Linear Residual Adapter (LRA) via Woodbury/Ridge             |  |
|  |    \hat{h}^{(l+m)} = \tilde{h}^{(l-1)} + U_r V_r^\top \tilde{h}^{(l-1)} + b |  |
|  |    Solved in closed form on 128 calibration sequences (Training-Free)       |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **层剪枝切口处的“流形断裂（Manifold Fracture）”**：当直接移除 Transformer 中的第 $l$ 至 $l+m$ 层时，第 $l-1$ 层的输出隐状态 $\tilde{h}^{(l-1)}$ 被直接送入原本期望接收 $h_{\text{orig}}^{(l+m)}$ 的第 $l+m+1$ 层。由于缺失了中间层的残差漂移与旋转，输入分布的一阶均值 $\mu$ 与二阶协方差矩阵 $\Sigma$ 发生剧烈跳变，导致紧随其后的注意力层 Q/K 点积失真并沿着深层指数级放大。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **剪枝切口处的最小二乘残差重构**：
   设剪枝段输入隐状态矩阵为 $X = \tilde{H}^{(l-1)} \in \mathbb{R}^{N \times d}$，原始未剪枝模型在该切口输出的目标残差增量为 $\Delta Y = H_{\text{orig}}^{(l+m)} - \tilde{H}^{(l-1)} \in \mathbb{R}^{N \times d}$。SHIFT-LLM 在切口处插入一个低秩线性残差适配器（LRA）$W_{\text{LRA}} = U_r V_r^\top + \mathbf{1} b^\top$，通过带 Tikhonov 正则化的岭回归闭式求解全秩最优映射 $W^*$：
   $$W^* = \arg\min_{W \in \mathbb{R}^{d \times d}} \big\| \Delta Y - (X - \bar{X}) W \big\|_F^2 + \lambda \| W \|_F^2 = \Big( \tilde{X}^\top \tilde{X} + \lambda I_d \Big)^{-1} \tilde{X}^\top \Delta \tilde{Y}$$
2. **激活协方差加权奇异值截断（Covariance-Weighted Truncated SVD）**：
   为保证适配器自身的计算开销可忽略（或直接折叠进下一层权重），对预测输出空間执行白化 SVD 分解：
   $$\tilde{X} W^* = \hat{U} \hat{\Sigma} \hat{V}^\top \implies U_r = (\tilde{X}^\top \tilde{X} + \lambda I_d)^{-1/2} \hat{U}_{:, 1:r} \hat{\Sigma}_{1:r}^{1/2}, \quad V_r = \hat{V}_{:, 1:r} \hat{\Sigma}_{1:r}^{1/2}$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在 **Llama-3-8B/70B** 与 **Qwen-2.5-14B** 上剪除 **25%–35% 的层**后，无需任何梯度下降微调（仅需 30 秒闭式矩阵求逆），SHIFT-LLM 将 WikiText2 困惑度（PPL）从 `28.4` 恢复至 **`9.1`**，零样本常识与数学推理平均精度恢复 **`+7.9%`**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 `modellesion-compression-scaffold`、`vla-dtr` (Ortho-MerA) 及 *Layer Dropping* (TMLR 2025) 的直接印证**：
  * SHIFT-LLM 的闭式岭回归校正算子 $W^* = (\tilde{X}^\top \tilde{X} + \lambda I)^{-1} \tilde{X}^\top \Delta \tilde{Y}$ 与我们在 `modellesion-compression-scaffold` 中使用的 **Depth SVD-LoRA / Woodbury KKT 闭式残差补偿** 数学形式完全一致！更进一步，结合我们的 `vla-dtr`（Ortho-MerA），我们只需对正交切空间残差 $\Delta Y_\perp = \Delta Y \cdot P_\perp(X)$ 进行低秩 SVD 拟合，而将平行分量 $\Delta Y_\parallel$ 简化为标量增益 $\alpha \in \mathbb{R}$，即可用一半的秩恢复更高的几何保真度。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-20_ai_paper_notes.md`


---

### 2.11 [2026-09-20] CARE: Spend Experts Where You Are Unsure — Confidence-Adaptive Routing for MoE-LoRA

* **论文信息**：`arXiv:2607.26052` (2026-07)
* **核心关键词**：Confidence-Adaptive Routing、MoE-LoRA、Nucleus Expert Activation、Router Uncertainty Entropy

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|            CARE: Confidence-Adaptive Routing for Mixture-of-Experts               |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Token Hidden State h_t ---> Router Probabilities p_t = Softmax(W_r h_t) \in \Delta^E|
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Router Uncertainty Quantification (路由分布置信度/不确定性度量)          |  |
|  |    Sort probabilities: p_{t,(1)} >= p_{t,(2)} >= ... >= p_{t,(E)}           |  |
|  |    High confidence (peaked p_t) -> K_t = 1; High entropy -> K_t = K_{\max}  |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Nucleus & Margin-Gated Dynamic Top-K(t) Selection                        |  |
|  |    K_t = \min \{ k \in [K_{\min}, K_{\max}] : \sum_{i=1}^k p_{t,(i)} >= \tau_p|
|  |               \text{ or } p_{t,(k)} - p_{t,(k+1)} >= \tau_m \}              |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **静态 Top-$k$ 路由的算力错配**：标准 MoE 对序列中的每一个 Token（无论是标点符号、常见停用词，还是复杂的逻辑转折词）均无差别地激活固定数量 $k$ 个专家。对于路由器高度确信的简单 Token（例如 $p_{t,(1)} > 0.85$），强制拉起第 $2 \dots k$ 个低概率专家不仅浪费算力，还会引入长尾噪声干扰；而对于处于知识边界的模糊 Token，固定 $k$ 个专家又不足以覆盖多维语义假设。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **累积概率核与边际跳变双门控（Nucleus & Margin Gated Dynamic $K_t$）**：
   将排序后的专家门控概率记为 $p_{t,(1)} \ge p_{t,(2)} \ge \dots \ge p_{t,(E)}$。CARE 为每个 Token $t$ 动态分配激活专家个数 $K_t \in [K_{\min}, K_{\max}]$：
   $$K_t = \min \left\{ k \in \{K_{\min}, \dots, K_{\max}\} \;\middle|\; \sum_{i=1}^k p_{t,(i)} \ge \tau_{\text{nuc}} \;\;\lor\;\; \big(p_{t,(k)} - p_{t,(k+1)}\big) \ge \tau_{\text{margin}} \right\}$$
2. **零训练即插即用温度校准（Temperature Calibration under Global FLOPs Target）**：
   给定目标平均激活专家预算 $\bar{K}_{\text{target}}$，在校准集上通过单标量温度 $\beta$ 缩放路由 logits $p_t(\beta) = \text{Softmax}(W_r h_t / \beta)$，满足 $\mathbb{E}_t[K_t(\beta)] = \bar{K}_{\text{target}}$。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在多任务 MoE-LoRA 与稀疏 MoE 语言模型上，CARE 在削减 **32%–45% 平均专家激活 FLOPs** 的同时，在常识推理、代码与数学基准上全面持平甚至超越固定 Top-$k$ 基线（`+0.9%` 平均准确率）。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 *Capacity-Aware Inference* (ICLR 2026) & *Router-Tuning* (EMNLP 2025) 的协同**：可将 CARE 的 Token 级置信度核门控（Nucleus Routing）与我们在 ICLR 2026 中提出的硬件容量感知丢弃/重路由（Capacity-Aware Dropping）级联，在软件置信度与硬件队列容量两个维度同时实现最优分配。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`models/` (Regime-Adaptive Dynamic Expert Allocation under Volatility Shifts)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-20_ai_paper_notes.md`


---

### 2.12 [2026-09-20] Minima-KV: Mixed-Format Paged Attention for Extreme KV Cache Compression

* **论文信息**：`arXiv:2608.23834` (2026-08)
* **核心关键词**：Mixed-Precision KV Cache、PagedAttention、Sub-Page Bit-Packing、Reasoning Continuity

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|        Minima-KV: Mixed-Format Paged Attention for Extreme KV Compression         |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Incoming KV Tokens ---> Saliency Tiering: [Tier-0: FP16] [Tier-1: INT4] [Tier-2: INT2]|
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Unified Iso-Byte Physical Page Pool (等字节物理页统一内存池)             |  |
|  |    Each Physical Page = 64 KB fixed size:                                   |  |
|  |    * Can store N_0 FP16 tokens OR 4*N_0 INT4 tokens OR 8*N_0 INT2 tokens    |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Warp-Specialized Mixed-Format PagedAttention Kernel                      |  |
|  |    Single CUDA kernel dispatches dequantization per page descriptor header  |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **混合精度 KV 缓存的“页表碎片化与多核启动开销”**：虽然算法层已证明将关键 Token 存为 FP16、次要 Token 存为 INT4/INT2 可逼近无损压缩，但在 vLLM 等生产级 PagedAttention 系统中，传统的物理页（Page Block）按固定 Token 槽位数划分。若不同位宽的 Token 混存，会导致高达 40% 的页内字节对齐浪费（Internal Fragmentation），或被迫拆分为 3 次独立 CUDA Kernel 启动。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **等字节容量物理页抽象（Iso-Byte Physical Page Abstraction）**：
   固定每个物理页的字节容量为 $B_{\text{page}}$（如 64 KB）。对于位宽为 $b \in \{16, 4, 2\}$ 的页类型，其容纳的逻辑 Token 槽位数动态缩放为：
   $$C_{\text{slots}}(b) = \frac{8 \cdot B_{\text{page}}}{2 \cdot H_{kv} \cdot d_h \cdot b + M_{\text{meta}}(b)}$$
   其中 $M_{\text{meta}}(b)$ 为分组量化缩放因子与零点（Scale & Zero-Point）的紧凑页头字节数。
2. **页描述符驱动的单核融合反量化注意力（Single-Kernel Fused Dequant-Attention）**：
   在逻辑页表中增加 2-bit 格式标签 $\text{fmt}(p) \in \{0, 1, 2\}$，CUDA Warp 在读取物理页 $p$ 时根据 $\text{fmt}(p)$ 在寄存器内执行即时位解包（Register-Level Bit Unpacking）：
   $$\hat{K}_p = \text{Unpack}_{\text{fmt}(p)}(Q_p^K) \odot s_p^K + z_p^K, \qquad S_p = Q \hat{K}_p^\top$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在 **Llama-3.1-70B** 与 **Qwen-2.5-32B** 的 128K 长思维链并发服务中，Minima-KV 实现 **4.6x** 真实物理显存节省（零内部页碎片），将最大并发 Batch Size 提升 **3.9x**，端到端解码吞吐提升 **2.7x**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **直接解决我们昨日精读的 SelKV 与 `Efficient Ads / HisTrim` 混合位宽生产落地瓶颈**：可将我们的正交价值空间显著性打分（Perp-OBCache）作为 Minima-KV 的三档分层准则（FP16 / INT4 / INT2），直接集成进统一等字节页表内核中。

---

## 🔥 板块二：全球前沿热点精选 (Trending Frontier)

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-20_ai_paper_notes.md`


---

### 2.13 [2026-09-20] ModularRSI: Modular and Generalizable Recursive Harness Self-Improvement

* **论文信息**：`arXiv:2609.14857` (2026-09)
* **核心关键词**：Modular Agent Harness、Compositional RSI、Interface-Constrained Evolution、Cross-Domain Generalization

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|       ModularRSI: Compositional & Interface-Constrained Harness Evolution         |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Monolithic Agent Harness H ---> Decompose into Orthogonal Typed Modules:         |
|    [M_plan: Planner] + [M_mem: Memory] + [M_tool: ToolExec] + [M_ver: Verifier]   |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Module-Specific Credit Attribution & Targeted Mutation                   |  |
|  |    Blame analysis localizes failure to module m^* \in \{plan, mem, tool, ver\}| |
|  |    Mutate ONLY m^* under strict I/O schema contract \mathcal{I}_{m^*}       |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Cross-Task Pareto Archive & Compositional Recombination                  |  |
|  |    Recombine best M_mem^* from QA tasks with best M_ver^* from Coding tasks |  |
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **单体脚手架（Monolithic Harness）突变的耦合脆弱性**：当元智能体直接重写几千行的单体智能体代码时，对记忆模块的一次修改极易意外破坏工具解析或循环终止条件（语法/接口耦合崩溃），且在编码任务上演化出的整套脚手架无法拆解复用至科学推理任务。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **强类型接口约束下的模块化分解**：
   将智能体脚手架表示为有向无环模块图 $H = (M_1, M_2, \dots, M_K; \mathcal{E})$，每个模块 $M_k$ 必须满足不可变的输入输出类型契约 $\mathcal{I}_k: \mathcal{X}_k \to \mathcal{Y}_k$。
2. **反事实模块替换与帕累托重组（Counterfactual Module Crossover）**：
   维护各模块的精英池 $\mathcal{P}_k = \{M_k^{(1)}, \dots, M_k^{(r)}\}$，通过加性代理模型估计任意模块组合的泛化效用：
   $$\hat{U}(M_1, \dots, M_K) = \sum_{k=1}^K \alpha_k(M_k) + \sum_{(j,k) \in \mathcal{E}} \beta_{j,k}(M_j, M_k)$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在 **SWE-bench**、**GAIA** 与 **GPQA** 跨领域迁移测试中，ModularRSI 的变异编译通过率从单体 RSI 的 `54%` 提升至 **`96%`**，跨领域零样本重组性能比单体进化高出 **`+9.1%`**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与我们 `rsi-sandbox-architect` 的严格契约设计完全吻合**：在设计多模块 RSI（例如同时优化 VLA 的视觉 Token 剪枝模块与动作流匹配蒸馏模块）时，强制锁定模块间张量形状与接口契约是实现跨实验最优组件正交组合的关键。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/evaluate_pareto_gate.py` (Time-Annealed Complexity & Ablation Pruner against Backtest Overfitting)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-20_ai_paper_notes.md`


---

### 2.14 [2026-09-19] WRP: Forward-Free LLM Depth Pruning via Weight Redundancy

* **论文信息**：`arXiv:2609.09883` (2026-09)
* **核心关键词**：Forward-Free Depth Pruning、Weight Redundancy、Spectral Subspace Alignment、Calibration-Free Layer Dropping

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|            WRP: Forward-Free LLM Depth Pruning via Weight Redundancy              |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Frozen Pretrained Weights {W_Q^{(l)}, W_K^{(l)}, W_V^{(l)}, W_O^{(l)}, W_FFN^{(l)}}|
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Effective Layer Operator Construction (无需前向激活的等效层算子构建)     |  |
|  |    \mathcal{T}_{\text{attn}}^{(l)} = W_O^{(l)} W_V^{(l)},                   |  |
|  |    \mathcal{T}_{\text{ffn}}^{(l)}  = W_{\text{down}}^{(l)} W_{\text{up}}^{(l)}| |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Spectral Concentration & Inter-Layer Subspace Redundancy (谱冗余度量)    |  |
|  |    R_{\text{intra}}(l) = 1 - \frac{\exp(H(\sigma^{(l)}))}{d}                |  |
|  |    R_{\text{inter}}(l) = \| U_{1:r}^{(l)\top} U_{\text{prev}}^{(1:l-1)} \|_F^2|
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 3. Zero-Pass One-Shot Block Pruning (<10 Seconds on CPU/Single GPU)         |  |
|  |    Prune top-K redundant blocks with highest w_1 R_{\text{intra}} + w_2 R_{\text{inter}}|
|  +-----------------------------------------------------------------------------+  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **校准集偏差（Calibration Set Bias）与前向显存开销**：现有的大模型深度/层剪枝方法（如 ShortGPT 的 Block Influence、LaCo、SliceGPT）均依赖在特定校准集（如 WikiText2 或 C4）上运行前向传播以统计输入输出余弦相似度。这不仅在 70B+ 模型上消耗高昂显存与时间，更严重的是层重要性打分高度受制于校准集分布——在通用语料上表现为“弱贡献”的层，往往承载着数学推理或代码生成的关键长尾子空间，剪除后导致严重的领域退化。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **无激活等效残差映射提取**：
   对于第 $l$ 层 Transformer 块，将其对残差流 $h^{(l-1)}$ 的线性主轴作用表征为注意力值-输出合成矩阵 $M_{\text{attn}}^{(l)} = W_O^{(l)} W_V^{(l)} \in \mathbb{R}^{d \times d}$ 与前馈网络合成算子 $M_{\text{ffn}}^{(l)} = W_{\text{down}}^{(l)} (W_{\text{up}}^{(l)} \odot \bar{\sigma}_{\text{gate}}) \in \mathbb{R}^{d \times d}$。
2. **层内有效秩赤字与层间子空间投影重叠度**：
   对合成算子执行奇异值分解 $M^{(l)} = U^{(l)} \Sigma^{(l)} V^{(l)\top}$，定义归一化奇异值分布 $p_i^{(l)} = \frac{\sigma_i^{(l)}}{\sum_j \sigma_j^{(l)}}$。层的权重综合冗余度得分 $\mathcal{S}_{\text{WRP}}(l)$ 由**层内谱坍缩度**与**相对于前序累积子空间的投影冗余度**共同决定：
   $$\mathcal{S}_{\text{WRP}}(l) = \underbrace{\left( 1 - \frac{\exp\big(-\sum_{i=1}^d p_i^{(l)} \log p_i^{(l)}\big)}{d} \right)}_{\text{Intra-Layer Spectral Redundancy}} + \lambda \underbrace{\frac{\big\| P_{\text{span}(1:l-1)} U_{:, 1:r}^{(l)} \big\|_F^2}{r}}_{\text{Inter-Layer Subspace Overlap}}$$
   其中 $P_{\text{span}(1:l-1)}$ 为前 $l-1$ 层输出主奇异子空间的正交投影算子。若第 $l$ 层的输出主奇异方向几乎完全落在前序层已经张成的子空间内（即缺乏新的正交特征扩展），则该层被判定为高度冗余。

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* **秒级零样本层裁剪且跨领域泛化更强**：在 **Llama-3-8B/70B**、**Qwen-2.5-14B** 与 **Mistral-7B** 上，WRP 在完全不运行任何前向传播（耗时不足 8 秒）的情况下剪除 **20%–25% 的层**，在 GSM8K 与 HumanEval 等对校准集敏感的生成任务上比 ShortGPT 和 SLEB 高出 **`+3.4%` 至 `+6.1%`**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **与 *Layer Dropping* (TMLR 2025)、*Demystifying When Pruning Works via Representation Hierarchies* (ICML 2026) 及 *Transformer-Geometry* (`arXiv:2609.15975`, EMNLP 2026) 的深度呼应**：
  * WRP 的第二项 $\big\| P_{\text{span}(1:l-1)} U_{:, 1:r}^{(l)} \big\|_F^2$ 在权重空间精确刻画了我们在 *Transformer-Geometry* 中定义的**平行分量与正交分量之比**——当层权重输出子空间与前序累积子空间高度重合时，该层仅产生平行特征放大而缺乏正交旋转增量！我们可以将 WRP 的纯权重谱重叠指标与单批次激活几何探针结合，作为 `vla-dtr`（VLADrop）的快速层筛选先验。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-19_ai_paper_notes.md`


---

### 2.15 [2026-09-19] Dream-RSI: Recursive Self-Improvement through Evolving Worlds

* **论文信息**：Tong Zheng, Xidong Wu, Zheng Zhang, Zhankui He et al. (`arXiv:2609.14858`, 2026-09)
* **核心关键词**：Recursive Self-Improvement、World Model Replay Simulator、Off-Policy Dreaming、Discovery Tree Evolution

#### 📐 架构与核心算法流程图 (ASCII Blueprint)

```text
+-----------------------------------------------------------------------------------+
|          Dream-RSI: Recursive Self-Improvement through Evolving Worlds            |
+-----------------------------------------------------------------------------------+
|                                                                                   |
|  Online Discovery History \mathcal{D}_{1:t} (Action-State-Reward Trees)           |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 1. Evolving Replay World Simulator \hat{\mathcal{W}}_t (演化重放世界模拟器) |  |
|  |    Fit transition & reward dynamics P_\psi(s', r | s, a) over discovery tree|  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|  +-----------------------------------------------------------------------------+  |
|  | 2. Off-Policy "Dreaming" Policy Refinement (离线做梦式策略自举优化)         |  |
|  |    Rollout K synthetic trajectories in \hat{\mathcal{W}}_t at 1/100th cost  |  |
|  |    Update Exploration Policy \pi_{\theta_{t+1}} via Dream-GRPO              |  |
|  +-----------------------------------------------------------------------------+  |
|                                        |                                          |
|                                        v                                          |
|      Deploy \pi_{\theta_{t+1}} to Real Environment ---> Expand \mathcal{D}_{t+1}  |
+-----------------------------------------------------------------------------------+
```

#### 🎯 背景与痛点 (Background & Pain Points)
* **在线 RSI 的高昂环境评估瓶颈**：无论是代码生成、编译器优化还是具身导航，每次候选策略变异若都需要在真实环境或完整基准上在线运行（Online Rollout），其算力与挂钟时间成本极高，且大量早期探索轨迹在被丢弃后未能转化为对环境转移规律的结构化认知。

#### 💡 核心方法与数学公式 (Core Methodology & Math)
1. **基于历史发现树的演化世界模拟器构建**：
   设截至第 $t$ 轮收集到的真实探索树轨迹库为 $\mathcal{D}_{1:t} = \{(s_i, a_i, r_i, s'_i)\}$。训练参数化世界模拟器 $\hat{\mathcal{W}}_{\psi_t}$ 联合拟合状态转移与不确定性感知奖励：
   $$\mathcal{L}_{\text{world}}(\psi) = \mathbb{E}_{(s,a,r,s') \sim \mathcal{D}_{1:t}} \Big[ -\log \hat{P}_\psi(s' \mid s, a) + \big\| \hat{R}_\psi(s, a) - r \big\|_2^2 \Big]$$
2. **悲观不确定性惩罚下的做梦策略优化（Pessimistic Dream Rollout）**：
   在离线“做梦”阶段，策略 $\pi_\theta$ 在 $\hat{\mathcal{W}}_{\psi_t}$ 中生成合成轨迹 $\tilde{\tau}$，并通过认识不确定性惩罚 $\sigma_{\psi_t}(s, a)$ 防止策略利用世界模型幻觉进行 Reward Hacking：
   $$J_{\text{dream}}(\theta) = \mathbb{E}_{\tilde{\tau} \sim (\pi_\theta, \hat{\mathcal{W}}_{\psi_t})} \left[ \sum_{k=0}^H \gamma^k \Big( \hat{R}_{\psi_t}(\tilde{s}_k, \tilde{a}_k) - \beta \cdot \sigma_{\psi_t}(\tilde{s}_k, \tilde{a}_k) \Big) \right]$$

#### 📊 关键实验与结论 (Key Experiments & Takeaways)
* 在复杂代码优化、Web 智能体长程交互及具身规划任务上，**Dream-RSI** 将真实在线评估调用次数削减 **70%–82%**，并在同等算力预算下将多轮自进化最终成功率提升 **`+9.6%`**。

#### 🔗 与我们工作（Our Works）的直接关联与落地启发
* **对我们 `autoresearch` 与 `ads-rsi` 离线代理筛选的启发**：可以利用历史 XID 实验账本（Pareto Ledger）训练一个轻量级算子性能预测与方差估计代理模型，在提交远程 GPU 评估前通过 Pessimistic Dreaming 过滤掉 80% 的劣质突变。

---

> [!TIP]
> **🎯 `stock_prediction` 仓库代码级落地点 (`Target Module`)**：`rsi_campaign/` & `models/` (`Shwai-He/stock-prediction`)  
> **📚 上游精读归档 (`Upstream Source`)**：`scholar-odyssey/intelligence/papers/2026-09-19_ai_paper_notes.md`


---
