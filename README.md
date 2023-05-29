# Federated Learning System Literature

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

A curated list of system-level optimization approaches on synchronous federated learning.

This repository serves as a complement of the survey below.

[**Towards Efficient Synchronous Federated Training: A Survey on System Optimization Strategies** (IEEE TBD 2022)](https://ieeexplore.ieee.org/document/9780218)

````bibtex
@article{jiang2022towards,
  author={Jiang, Zhifeng and Wang, Wei and Li, Bo and Yang, Qiang},
  journal={IEEE Transactions on Big Data}, 
  title={Towards Efficient Synchronous Federated Training: A Survey on System Optimization Strategies}, 
  year={2023},
  volume={9},
  number={2},
  pages={437-454},
  doi={10.1109/TBDATA.2022.3177222}}
````

If you feel this repository is helpful, please help to cite the survey above.

## How to Search?
Search keywords like conference name (e.g., ```OSDI```), target phase (e.g., ```Client Selection```), or performance metric (e.g., ```Communication Cost```) over the webpage to quickly locate related papers.

## Quick Links
**Recent Optimization Approaches:**
* [Optimizing the Selection Phase](#21-optimizing-the-selection-phase): At the beginning of each round, the server waits for a sufficient number of clients with
eligible status (i.e., currently charging and connected to an unmetered network) to check in. The server then selects a subset of them based on certain strategies (e.g., randomly or selectively) for participation, and notifies the others to reconnect later.
* [Optimizing the Configuration Phase](#22-optimizing-the-configuration-phase): The server next sends the global model status and configuration profiles (e.g., the number of local epochs or the reporting deadline) to each of the selected clients. Based on the instructed configuration, the clients perform local model training independently with their private data.
* [Optimizing the Reporting Phase](#23-optimizing-the-reporting-phase): The server then waits for the participating clients to report local updates until reaching the predefined deadline. The current round is aborted if no enough clients report in time. Otherwise, the server aggregates the received local updates, uses the aggregate to update the global model status, and concludes the round.

**Measuring and Benchmarking Tools:**
* [Measurement-Based Research](#31-measurement-based-research)
* [Benchmarking Suite](#32-benchmarking-suites)

## 2 Recent Optimization Approaches
### 2.1 Optimizing the Selection Phase
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **AutoFL: Enabling heterogeneity-aware energy efficient federated learning** | Co-design (Fine-grained) | ACM MICRO | [Link](https://dl.acm.org/doi/abs/10.1145/3466752.3480129) |
| 2021 | **Oort: Efficient federated learning via guided participant selection** | Co-design (Fine-grained) | USENIX OSDI | [Link](https://www.usenix.org/conference/osdi21/presentation/lai) |
| 2021 | **Client selection for federated learning with non-IID data in mobile edge computing** | Partial optimization (Statistics-oriented) | IEEE Access | [Link](https://ieeexplore.ieee.org/document/9345723) |
| 2020 | **TiFL: A tier-based federated learning system** | Co-design (Coarse-grained) | ACM HDPC | [Link](https://dl.acm.org/doi/abs/10.1145/3369583.3392686) |
| 2020 | **Optimizing federated learning on non-IID data with reinforcement learning** | Partial optimization (statistics-oriented) | IEEE INFOCOM | [Link](https://ieeexplore.ieee.org/document/9155494) |
| 2019 | **Client selection for federated learning with heterogeneous resources in mobile edge** | Partial optimization (system-oriented) | IEEE ICC | [Link](https://ieeexplore.ieee.org/document/8761315) |


### 2.2 Optimizing the Configuration Phase
#### 2.2.1 Synchronization Frequency Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **Communication-efficient federated learning with adaptive parameter freezing** | Parameter-level | IEEE ICDCS | [Link](https://ieeexplore.ieee.org/document/9546506) |
| 2020 | **Communication-efficient federated deep learning with layerwise asynchronous model update and temporally weighted aggregation** | Layer-level | IEEE TNNLS | [Link](https://ieeexplore.ieee.org/document/8945292) |
| 2019 | **CMFL: Mitigating communication overhead for federated learning** | Client-level | IEEE ICDCS | [Link](https://ieeexplore.ieee.org/document/8885054) |
| 2018 | **Efficient decentralized deep learning by dynamic model averaging** | Client-level | ECML-PKDD | [Link](https://link.springer.com/chapter/10.1007/978-3-030-10925-7_24) |

#### 2.2.2 Model Update Size Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2020 | **FetchSGD: Communication-efficient federated learning with sketching** | Sketch | ICML | [Link](https://proceedings.mlr.press/v119/rothchild20a.html) |
| 2019 | **Compressing Gradient Optimizers via Count-Sketches** | Sketch | ICML | [Link](https://proceedings.mlr.press/v97/spring19a.html) |
| 2019 | **Communication-efficient distributed SGD with sketching** | Sketch | NeurIPS | [Link](https://papers.nips.cc/paper_files/paper/2019/hash/75da5036f659fe64b53f3d9b39412967-Abstract.html) |
| 2019 | **Error feedback fixes SignSGD and other gradient compression schemes** | Quantization | ICML | [Link](https://proceedings.mlr.press/v97/karimireddy19a.html) |
| 2019 | **SignSGD with majority vote is communication efficient and fault tolerant** | Quantization | ICLR | [Link](https://openreview.net/forum?id=BJxhijAcY7) |
| 2019 | **A distributed synchronous SGD algorithm with global top-k sparsification for low bandwidth networks** | Sparsification | IEEE ICDCS | [Link](https://www.computer.org/csdl/proceedings-article/icdcs/2019/251900c238/1ezRT3vzfcA) |
| 2018 | **Sparsified SGD with memory** | Sparsification | NeurIPS | [Link](https://proceedings.neurips.cc/paper_files/paper/2018/hash/b440509a0106086a67bc2ea9df0a1dab-Abstract.html) |
| 2018 | **Deep gradient compression: Reducing the communication bandwidth for distributed training** | Sparsification | ICLR | [Link](https://openreview.net/forum?id=SkhQHMW0W) |
| 2018 | **Gradient sparsification for communication-efficient distributed optimization** | Sparsification | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2018/hash/3328bdf9a4b9504b9398284244fe97c2-Abstract.html) |
| 2018 | **SketchML: Accelerating distributed machine learning with data sketches** | Sketch | ACM SIGMOD | [Link](https://dl.acm.org/doi/10.1145/3183713.3196894) |
| 2018 | **Error compensated quantized SGD and its applications to large-scale distributed optimization** | Quantization | ICML | [Link](https://arxiv.org/abs/1806.08054) |
| 2017 | **Gaia: Geo-distributed machine learning approaching LAN speeds** | Client-level | USENIX NSDI | [Link](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/hsieh) |
| 2017 | **Sparse communication for distributed gradient descent** | Sparsification | ACL EMNLP | [Link](https://aclanthology.org/D17-1045/) |
| 2017 | **TernGrad: Ternary gradients to reduce communication in distributed deep learning** | Quantization | NeurIPS | [Link](https://papers.nips.cc/paper_files/paper/2017/hash/89fcd07f20b6785b92134bd6c1d0fa42-Abstract.html) |
| 2017 | **QSGD: Communication-efficient SGD via gradient quantization and encoding** | Quantization | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2017/hash/6c340f25839e6acdc73414517203f5f0-Abstract.html) |

#### 2.2.3 Training Latency Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **Accelerating DNN training in wireless federated edge learning systems** | Load balancing (Communication) | IEEE JSAC | [Link](https://ieeexplore.ieee.org/document/9252924) |
| 2021 | **HeteroFL: Computation and communication efficient federated learning for heterogeneous clients** | Load balancing (Optimization step) | ICLR | [Link](https://openreview.net/forum?id=TNkPBBYFkXg) |
| 2021 | **Towards efficient scheduling of federated mobile devices under computational and statistical heterogeneity** | Load balancing (Data amount) | IEEE TPDS | [Link](https://www.computer.org/csdl/journal/td/2021/02/09195793/1n7i58g5GlG) |
| 2020 | **Federated optimization in heterogeneous networks** | Load balancing (Optimization step) | MLSys | [Link](https://proceedings.mlsys.org/paper_files/paper/2020/hash/38af86134b65d0f10fe33d30dd76442e-Abstract.html) |
| 2020 | **Resource allocation in mobility-aware federated learning networks: A deep reinforcement learning approach** | Load balancing (Data amount) | IEEE WF-IoT | [Link](https://ieeexplore.ieee.org/document/9221089) | 
| 2019 | **Efficient training management for mobile crowd-machine learning: A deep reinforcement learning approach** | Load balancing (Data amount) | IEEE WCL | [Link](https://ieeexplore.ieee.org/document/8716527) |

#### 2.2.4 Training Round Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **Breaking the centralized barrier for cross-device federated learning** | Client bias reduction | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2021/hash/f0e6be4ce76ccfa73c5a540d992d0756-Abstract.html) |
| 2021 | **Federated learning based on dynamic regularization** | Client bias reduction | ICLR | [Link](https://openreview.net/forum?id=B7v4QMR6Z9w) |
| 2020 | **Federated learning via posterior averaging: A new perspective and practical algorithms** | Client bias reduction | ICLR | [Link](https://openreview.net/forum?id=GFsU8a0sGB) |
| 2020 | **SCAFFOLD: Stochastic controlled averaging for federated learning** | Client bias reduction | ICML | [Link](https://proceedings.mlr.press/v119/karimireddy20a.html) |
| 2020 | **Federated optimization in heterogeneous networks** | Client bias reduction | MLSys | [Link](https://proceedings.mlsys.org/paper_files/paper/2020/hash/38af86134b65d0f10fe33d30dd76442e-Abstract.html) |
| 2020 | **Accelerating federated learning via momentum gradient descent** | Optimizer state synchronization | IEEE TPDS | [Link](https://ieeexplore.ieee.org/document/9003425) |
| 2020 | **Federated accelerated stochastic gradient descent** | Optimizer state synchronization | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2020/hash/39d0a8908fbe6c18039ea8227f827023-Abstract.html) |
| 2019 | **FedDANE: A federated Newton-type method** | Client bias reduction | IEEE ACSSC | [Link](https://par.nsf.gov/servlets/purl/10129424) | 
| 2019 | **On the linear speedup analysis of communication efficient momentum SGD for distributed nonconvex optimization** | Optimizer state synchronization | ICML | [Link](https://proceedings.mlr.press/v97/yu19d.html) |

### 2.3 Optimizing the Reporting Phase

#### 2.3.1 Aggregation Latency Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2022 | **LightSecAgg: Rethinking secure aggregation in federated learning** | Lightweight privacy-preserving aggregation | MLSys | [Link](https://proceedings.mlsys.org/paper/2022/hash/d2ddea18f00665ce8623e36bd4e3c7c5-Abstract.html) |
| 2021 | **Flashe: Additively symmetric homomorphic encryption for cross-silo federated learning** | Lightweight privacy-preserving aggregation | arXiv | [Link](https://arxiv.org/abs/2109.00675) |
| 2021 | **Turbo-aggregate: Breaking the quadratic aggregation barrier in secure federated learning** | Lightweight privacy-preserving aggregation | IEEE JSAIT | [Link](https://eprint.iacr.org/2020/167) |
| 2020 | **FastSecAgg: Scalable secure aggregation for privacy-preserving federated learning** | Lightweight privacy-preserving aggregation | ICML Workshop | [Link](https://arxiv.org/abs/2009.11248) |
| 2020 | **Secure single-server aggregation with (poly) logarithmic overhead** | Lightweight privacy-preserving aggregation | ACM CCS | [Link](https://eprint.iacr.org/2020/704) |
| 2020 | **BatchCrypt: Efficient homomorphic encryption for cross-silo federated learning** | Lightweight privacy-preserving aggregation | USENIX ATC | [Link](https://www.usenix.org/conference/atc20/presentation/zhang-chengliang) |
| 2020 | **Accelerating federated learning over reliability-agnostic clients in mobile edge computing systems** | Hierarchical aggregation | IEEE TPDS | [Link](https://ieeexplore.ieee.org/document/9272671) |
| 2020 | **Hierarchical federated learning across heterogeneous cellular networks** | Hierarchical aggregation | IEEE ICASSP | [Link](https://ieeexplore.ieee.org/document/9054634) |
| 2020 | **Client-edge-cloud hierarchical federated learning** | Hierarchical aggregation | IEEE ICC | [Link](https://ieeexplore.ieee.org/document/9148862) |

#### 2.3.2 Adaptive Aggregation
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **Adaptive federated optimization** | Server-side optimizer | ICLR | [Link](https://openreview.net/forum?id=LkFG3lB13U5) |
| 2020 | **SlowMo: Improving communication-efficient distributed SGD with slow momentum** | Server-side optimizer | ICLR | [Link](https://openreview.net/forum?id=SkxJ8REYPH) |
| 2019 | **Measuring the effects of nonidentical data distribution for federated visual classification** | Server-side optimizer | NeurIPS Workshop | [Link](https://arxiv.org/abs/1909.06335) |

## 3 Measuring and Benchmarking Tools
### 3.1 Measurement-Based Research
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2021 | **Characterizing impacts of heterogeneity in federated learning upon large-scale smartphone data** | Mobile | ACM WWW | [Link](https://dl.acm.org/doi/abs/10.1145/3442381.3449851) |

### 3.2 Benchmarking Suites
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2022 | **The OARF benchmark suite: Characterization and implications for federated learning systems** | Training datasets | ACM TIST | [Link](https://dl.acm.org/doi/full/10.1145/3510540) |
| 2022 | **FedScale: Benchmarking model and system performance of federated learning** | Training datasets | ICML Workshop | [Link](https://proceedings.mlr.press/v162/lai22a.html) |
| 2021 | **FATE: An industrial grade platform for collaborative learning with data protection** | Production systems and simulation platforms | ACM JMLR | [Link](https://www.jmlr.org/papers/volume22/20-815/20-815.pdf) |
| 2020 | **Flower: A friendly federated learning research framework** | Production systems and simulation platforms | arXiv | [Link](https://arxiv.org/abs/2007.14390) | 
| 2020 | **FedML: A research library and benchmark for federated machine learning** | Production systems and simulation platforms | NeurIPS Workshop | [Link](https://arxiv.org/abs/2007.13518) |
| 2018 | **Leaf: A benchmark for federated settings** | Training datasets | arXiv | [Link](https://arxiv.org/abs/1812.01097) |
