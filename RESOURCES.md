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
- [论文清单](#论文清单)
- [硬件与云平台](#硬件与云平台)
- [工具链](#工具链)
- [社区与信息源](#社区与信息源)

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

### 必读（按顺序）

**训练与并行**
1. Attention Is All You Need (2017) — Transformer 基础
2. ZeRO: Memory Optimizations Toward Training Trillion Parameter Models (2019)
3. ZeRO-Offload / ZeRO-Infinity
4. Megatron-LM: Training Multi-Billion Parameter Models (2019) — 张量并行
5. GPipe (2019) / PipeDream (2019) — 流水并行

**高效注意力与算子**
6. **FlashAttention** (2022) — 必读，理解 IO-aware 优化
7. FlashAttention-2 (2023)

**推理优化**
8. **Efficient Memory Management for Large Language Model Serving with PagedAttention** (vLLM, 2023) ⭐
9. Fast Inference from Transformers via Speculative Decoding (2023)
10. Orca: A Distributed Serving System for Transformer-Based Generative Models (2022) — Continuous Batching
11. SmoothQuant / GPTQ / AWQ — 量化

### 选读（按方向）
- 通信：Ring AllReduce 相关、NCCL 论文
- 编译器：TVM、MLIR、Triton 论文
- 存储：向量检索 HNSW、IVF
- 系统：Checkpointing、容错、调度

### 读论文的方法
1. 先读 Abstract + Intro + Conclusion（10 分钟，判断要不要细读）
2. 再看核心 Figure（通常一张图就是全部思想）
3. 然后推导关键公式
4. **最后一定动手实现或复现**——不然一周后全忘

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
