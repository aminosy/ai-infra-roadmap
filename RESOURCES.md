# 资源清单

> 按阶段分类。**不要囤资源**——每个阶段只挑 1-2 个主教材，其余作为查阅。

---

## 目录

- [阶段 1a：编程预热](#阶段-1a编程预热)
- [阶段 1b：系统基础](#阶段-1b系统基础)
- [阶段 2：GPU 与 CUDA](#阶段-2gpu-与-cuda)
- [阶段 3：模型与框架](#阶段-3模型与框架)
- [阶段 4：分布式训练](#阶段-4分布式训练)
- [阶段 5：推理系统](#阶段-5推理系统)
- [视频入门路径（零基础必看）](#视频入门路径零基础必看)
- [论文清单](#论文清单)
- [硬件与云平台](#硬件与云平台)
- [工具链](#工具链)
- [社区与信息源](#社区与信息源)

---

## 视频入门路径（零基础必看）

> 面向：**从没系统学过机器学习**的人。
> 目标不是"学完"，而是建立**画面感**——知道注意力在算什么、为什么它贵。
> ⚠️ 看完能回答下面的问题就够，**不要追求彻底搞懂**。

### 学习顺序

| 站 | 内容 | B 站搜索关键词 | 时长 | 看完应能回答 |
|---|---|---|---|---|
| 0 | 3Blue1Brown 神经网络系列（4 集） | `3Blue1Brown 神经网络` | 1.5–2h | 神经网络是怎么"学习"的？ |
| 1 | ⭐ **3Blue1Brown GPT 系列**（2 集） | `3Blue1Brown GPT` | 1–1.5h | 注意力在算什么？为什么每个词要看别的词？ |
| 2 | 李宏毅 机器学习 / 生成式 AI（精选 3–4 集） | `李宏毅 机器学习` | 3–4h | Q、K、V 分别是什么角色？ |
| 3 | 李沐《动手学深度学习》注意力机制 | `跟李沐学AI` | 2–3h | 注意力的计算量为什么是 O(n²)？ |
| 4 | 王木头学科学（补充视角，可选） | `王木头 Transformer` | 2–3h | 换个说法还能讲清楚吗？ |

### 三条路径

| 路径 | 内容 | 总耗时 | 适合 |
|---|---|---|---|
| **最小必要** | 0 + 1 | 2.5–3.5h | **W1 阶段就用这个** |
| **推荐** | 0 + 1 + 2 | 6–8h | 想打牢基础 |
| 完整 | 全部 | 12–16h | 阶段 3 系统学时 |

### 三条纪律

1. **视频可以 1.5 倍速，但"注意力"那一集必须原速** —— 动画信息密度大
2. **一天最多两集**，看完停下来想一想，别一口气刷完
3. **答不上对应问题就重看，别往后跳**

### 配套图文（比论文好懂 10 倍）

| 材料 | 网址 |
|---|---|
| The Illustrated Transformer（英文原版） | https://jalammar.github.io/illustrated-transformer/ |
| The Illustrated Transformer（中文翻译 ①） | https://blog.csdn.net/yujianmin1990/article/details/85221271 |
| The Illustrated Transformer（中文翻译 ②） | https://blog.csdn.net/qq_36667170/article/details/124359818 |
| ⭐ Inside vLLM: Anatomy of a High-Throughput LLM Inference System | https://vllm.ai/blog/2025-09-05-anatomy-of-vllm |
| PagedAttention 原论文 | https://arxiv.org/abs/2309.06180 |
| vLLM 博客首页（持续更新） | https://vllm.ai/blog |

> ⚠️ **现在只读上面那篇 vLLM 文章的 PagedAttention 一节**，全文（41 分钟）留到阶段 5（W47）。

---

## 阶段 1a：编程预热

### Linux / 命令行
- 《The Linux Command Line》(William Shotts) — 免费 PDF，最佳入门
- 《鸟哥的 Linux 私房菜》 — 中文，查阅用
- 练习：MIT Missing Semester（命令行、Git、调试、性能工具）

### Git
- Pro Git（中文版免费）
- Learn Git Branching（交互式，练分支最有效）

### Python
- 《Python Crash Course》/《流畅的 Python》（进阶）
- CS61A（伯克利，讲得极好）
- numpy 官方 quickstart

### C 语言
- 《C Primer Plus》或 K&R《C 程序设计语言》
- 《C 和指针》— 指针部分讲得最透
- 必做：手写 `strlen/strcpy/memcpy`，用 gdb 调段错误

---

## 阶段 1b：系统基础

### 数据结构与算法
- 《算法（第 4 版）》(Sedgewick) — 图多、易懂
- 《剑指 Offer》+ LeetCode 中等题
- VisuAlgo（可视化）

### C++
- 《C++ Primer》（第 5 版）— 主教材
- 《Effective Modern C++》(Meyers) — 现代特性必读
- 《C++ Concurrency in Action》— 并发部分
- cppreference.com — 日常查阅

### 计算机系统 ⭐ 重中之重
- **《深入理解计算机系统》CSAPP** — 精读，Lab 全做
- CSAPP 官方 Lab：Data / Bomb / Attack / **Malloc** / Proxy / Cache
- CS61C（伯克利，体系结构）
- 《计算机组成与设计：硬件/软件接口》(Patterson)

### 操作系统
- **《操作系统导论》OSTEP** — 免费在线，中文版也有，最佳入门
- 《现代操作系统》(Tanenbaum)
- MIT 6.S081 / 6.828 — 动手写 OS 内核（时间充裕再做）

### 计算机网络
- 《计算机网络：自顶向下方法》
- 《UNIX 网络编程》(Stevens) — socket 部分

### 性能分析
- 《Systems Performance》(Brendan Gregg)
- perf / 火焰图入门

---

## 阶段 2：GPU 与 CUDA

### 主教材
- **《Programming Massively Parallel Processors》(PMPP)** — CUDA 圣经，第 4 版
- NVIDIA CUDA C Programming Guide（官方，查阅）
- CUDA C Best Practices Guide（官方）

### 课程
- UIUC ECE 408 / CS 483（CUDA 专项）
- Coursera: "CUDA at Scale for the Enterprise"

### Triton
- Triton 官方文档与 tutorials
- 推荐路径：先手写 CUDA，再用 Triton 重写同一个算子做对比

### 性能工具
- **Nsight Compute (`ncu`)** — kernel 级分析，必会
- **Nsight Systems (`nsys`)** — 时间线分析，看整体
- `nvidia-smi`、`nvprof`（旧）

### 关键概念自查
线程层次、warp、SIMT、内存层次、合并访问、bank conflict、occupancy、warp divergence、共享内存、异步拷贝

---

## 阶段 3：模型与框架

### 深度学习基础
- 李沐《动手学深度学习》(D2L) — 中文，免费
- Karpathy: **nanoGPT**（强烈推荐，从头手写 GPT）
- Karpathy: "Let's build GPT from scratch"（视频）
- 3Blue1Brown 的 Transformer 可视化

### PyTorch
- 官方 tutorials
- 《Deep Learning with PyTorch》
- 深入：读 `torch.autograd` 和 `torch.nn` 源码

### Transformer
- 原始论文《Attention Is All You Need》
- **The Illustrated Transformer** (Jay Alammar)
- The Annotated Transformer（逐行讲解代码）

---

## 阶段 4：分布式训练

### 通信
- NCCL 官方文档与用户指南
- 《MPI 并行程序设计》
- 集合通信原语可视化：搜索 "collective communication visualization"

### 框架
- **DeepSpeed** 官方文档与 tutorial
- **Megatron-LM** 官方 README 与代码
- PyTorch DDP / FSDP 官方文档
- Colossal-AI（中文文档友好）

### 书
- 《大规模语言模型：从理论到实践》（复旦，中文，免费）
- 《分布式机器学习：算法、理论与实践》

### 论文
见 [论文清单](#论文清单)

---

## 阶段 5：推理系统

### 框架源码（重点）
- **vLLM** ⭐ 主攻对象
- SGLang
- TensorRT-LLM
- llama.cpp（想学纯 C++ 推理实现看这个）

### 关键技术
- PagedAttention、Continuous Batching
- 量化：GPTQ、AWQ、SmoothQuant、llm.int8()
- 投机解码
- PD 分离（Prefill-Decode Disaggregation）

### 学习路径建议
```
先看论文理解"为什么" 
  → 再跑一遍框架看"什么效果"
  → 再读源码看"怎么实现"
  → 最后自己重写一个 mini 版
```

---

## 论文清单

> ⚠️ **不要现在读论文。** 每篇都标了「解锁阶段」——基础不牢时硬读只会浪费时间。
> 按阶段解锁，读完一篇就动手复现一次。

### 前置（阶段 3 解锁）

必须先有 Transformer 基础，否则后面全是天书。

| # | 论文 / 材料 | 年份 | 一句话 |
|---|---|---|---|
| 1 | **The Illustrated Transformer**（博客） | 2018 | 不是论文，但比论文好懂 10 倍，**先看这个** |
| 2 | Attention Is All You Need | 2017 | Transformer 的起点，一切的地基 |

### KV Cache 线（阶段 5 解锁）

> ⚠️ KV Cache 本身**没有「发明它的论文」**——它是自回归推理的工程常识：
> 生成第 N 个 token 时，前 N-1 个 token 的 K/V 不会变，所以不必重算。
> 这条线要读的是**围绕它显存问题的历代优化**。

| # | 论文 | 年份 | 解决的问题 |
|---|---|---|---|
| 3 | **Efficiently Scaling Transformer Inference** (Google) | 2022 | ⭐ 系统视角看推理：算力/访存瓶颈、KV Cache 成本分析。**理解推理的第一篇** |
| 4 | Fast Transformer Decoding: One Write-Head is All You Need | 2019 | MQA：多个 head 共享 K/V，直接砍掉 KV Cache 体积 |
| 5 | GQA: Training Generalized Multi-Query Transformer | 2023 | 分组查询注意力，MHA 与 MQA 的折中，Llama 2/3 都在用 |
| 6 | **PagedAttention / vLLM** | 2023 | ⭐ KV Cache 的显存管理，像操作系统分页一样管它 |

**想搞懂 KV Cache 本身，最好的材料其实不是论文：**
- vLLM 官方博客的 PagedAttention 图解
- 上面第 3 篇的 Introduction（对 KV Cache 成本的分析极其清楚）

### FlashAttention 线（阶段 5 解锁）

| # | 论文 | 年份 | 一句话 |
|---|---|---|---|
| 7 | Online normalizer calculation for softmax | 2018 | 在线 softmax —— FlashAttention 的核心技巧来源 |
| 8 | Self-attention Does Not Need O(n²) Memory | 2021 | 同样的思想，更早的表述 |
| 9 | **FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness** | 2022 | ⭐ **核心论文**。关键不是算法，是「别把中间结果写回显存」 |
| 10 | FlashAttention-2 | 2023 | 更好的并行与工作划分，速度大幅提升 |
| 11 | FlashAttention-3 | 2024 | 针对 Hopper 架构，异步执行 + 低精度 |

### KV Cache 压缩线（进阶，阶段 5 之后）

| # | 论文 | 年份 | 一句话 |
|---|---|---|---|
| 12 | StreamingLLM | 2023 | attention sink 现象，滑动窗口也能保持能力 |
| 13 | H2O: Heavy-Hitter Oracle | 2023 | 只保留重要的 KV，丢掉无关的 |

### 训练与并行（阶段 4 解锁）

| # | 论文 | 年份 | 一句话 |
|---|---|---|---|
| 14 | ZeRO: Memory Optimizations Toward Training Trillion Parameter Models | 2019 | 优化器状态/梯度/参数分片，省显存 |
| 15 | Megatron-LM | 2019 | 张量并行 |
| 16 | GPipe / PipeDream | 2019 | 流水并行与气泡 |
| 17 | Orca | 2022 | Continuous Batching 的系统实现 |
| 18 | Fast Inference from Transformers via Speculative Decoding | 2023 | 用算力换速度 |
| 19 | SmoothQuant / GPTQ / AWQ | 2022–23 | 量化 |

### 选读（按方向）
- 通信：Ring AllReduce 相关、NCCL 论文
- 编译器：TVM、MLIR、Triton 论文
- 存储：向量检索 HNSW、IVF
- 系统：Checkpointing、容错、调度

### 读论文的方法

**三遍法**（不要第一遍就想全懂）：
1. **第一遍**：Abstract + Intro + Conclusion + 所有图（10 分钟）→ 判断值不值得细读
2. **第二遍**：看核心 Figure，通常一张图就是全部思想；跳过公式
3. **第三遍**：推导关键公式，对照代码

**四条铁律：**
- 先读**图**，再读**公式**，最后读**证明**
- **读不懂是正常的**——前沿论文本来就是给同行看的，第一遍能抓住 20% 就够
- **一定动手复现**，不然一周后全忘
- 找不到感觉时，先去看**中文博客 / 视频讲解**，回来再读原文

---

## 硬件与云平台

### 分阶段策略

| 阶段 | 方案 | 成本 |
|---|---|---|
| W1–W22 | 现有电脑（集显也行） | 0 |
| W23–W24 | Google Colab 免费 T4 / Kaggle（每周 30h） | 0 |
| W25–W30 | 按小时租云单卡 | 几十元/次 |
| W37–W46 | 租云多卡，每次几小时 | 百元级 |
| W47 之后 | 建议自有一张卡（16G+ 显存） | 见下 |

### 云 GPU 平台

**国内**（便宜、延迟低）
- AutoDL、恒源云、矩池云、潞晨云

**国外**（更便宜但延迟高）
- Vast.ai、RunPod、Lambda Labs

**免费**
- Google Colab（T4）
- Kaggle Notebooks（每周 30 小时）
- **学校实验室集群** ← 最容易被忽视，先去问导师和师兄

### 自购配置建议（确定要坚持后再买）

| 部件 | 建议 | 理由 |
|---|---|---|
| GPU | 4060 Ti 16G / 二手 3090 24G | **显存 > 算力** |
| 内存 | 32GB 起，64GB 更佳 | 编译和容器极吃内存 |
| 硬盘 | 1TB NVMe | 模型数据集很大 |
| 系统 | Ubuntu 双系统或 WSL2 | Infra 开发在 Linux |

**不要买 Mac 学 Infra** —— M 系列不支持 CUDA，学不了阶段 2 的核心内容。

---

## 工具链

| 类别 | 工具 |
|---|---|
| 编辑器 | VS Code + Remote-SSH / CLion / vim |
| C++ 构建 | CMake、Make |
| 调试 | gdb、lldb、valgrind、ASAN/TSAN |
| 性能 | perf、Nsight Compute/Systems、torch.profiler |
| Python | conda / uv / venv、ruff、pytest |
| 容器 | Docker、nvidia-container-toolkit |
| 集群 | Kubernetes（阶段 6 用到再看） |
| 版本 | git、pre-commit |
| 实验管理 | wandb / tensorboard |

---

## 社区与信息源

### 必读博客
- **Lilian Weng** (lilianweng.github.io) — 综述质量极高
- **Chip Huyen** — ML 系统设计
- **Jay Alammar** — 可视化讲解
- **Horace He** — 编译与训练优化
- **PyTorch / vLLM 官方博客**

### 社区
- GitHub：给 vLLM / Triton / PyTorch 提 PR，是最高效的学习方式
- 知乎「大模型 infra」「CUDA 编程」话题
- 各类 Infra 技术群 / Discord

### 保持信息更新
- 关注 vLLM、SGLang、DeepSpeed 的 release notes
- MLsys 会议：MLSys、OSDI、SOSP、ASPLOS

---

## 一句话提醒

**资源是查的，不是读的。** 每个阶段只挑一本主教材精读，其余在遇到问题时去查。

囤 50 个收藏夹不会让你变成 Infra 工程师，写完项目 9 才会。
