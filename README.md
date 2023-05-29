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

## Quick Links
**Recent Optimization Approaches:**
* [Optimizing the Selection Phase](#21-optimizing-the-selection-phase): At the beginning of each round, the server waits for a sufficient number of clients with
eligible status (i.e., currently charging and connected to an unmetered network) to check in. The server then selects a subset of them based on certain strategies (e.g., randomly or selectively) for participation, and notifies the others to reconnect later.
* [Optimizing the Configuration Phase](#22-optimizing-the-configuration-phase): The server next sends the global model status and configuration profiles (e.g., the number of local epochs or the reporting deadline) to each of the selected clients. Based on the instructed configuration, the clients perform local model training independently with their private data.
* [Optimizing the Reporting Phase](#23-optimizing-the-reporting-phase): The server then waits for the participating clients to report local updates until reaching the predefined deadline. The current round is aborted if no enough clients report in time. Otherwise, the server aggregates the received local updates, uses the aggregate to update the global model status, and concludes the round.

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
| 2019 | **SignSGD with majority vote is communication efficient and fault tolerant** | Quantization | ICLR (Poster) | [Link](https://openreview.net/forum?id=BJxhijAcY7) |
| 2019 | **A distributed synchronous SGD algorithm with global top-k sparsification for low bandwidth networks** | Sparsification | IEEE ICDCS | [Link](https://www.computer.org/csdl/proceedings-article/icdcs/2019/251900c238/1ezRT3vzfcA) |
| 2018 | **Sparsified SGD with memory** | Sparsification | NeurIPS | [Link](https://proceedings.neurips.cc/paper_files/paper/2018/hash/b440509a0106086a67bc2ea9df0a1dab-Abstract.html) |
| 2018 | **Deep gradient compression: Reducing the communication bandwidth for distributed training** | Sparsification | ICLR (Poster) | [Link](https://openreview.net/forum?id=SkhQHMW0W) |
| 2018 | **Gradient sparsification for communication-efficient distributed optimization** | Sparsification | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2018/hash/3328bdf9a4b9504b9398284244fe97c2-Abstract.html) |
| 2018 | **SketchML: Accelerating distributed machine learning with data sketches** | Sketch | ACM SIGMOD | [Link](https://dl.acm.org/doi/10.1145/3183713.3196894) |
| 2018 | **Error compensated quantized SGD and its applications to large-scale distributed optimization** | Quantization | ICML | [Link](https://arxiv.org/abs/1806.08054) |
| 2017 | **Gaia: Geo-distributed machine learning approaching LAN speeds** | Client-level | USENIX NSDI | [Link](https://www.usenix.org/conference/nsdi17/technical-sessions/presentation/hsieh) |
| 2017 | **Sparse communication for distributed gradient descent** | Quantization | ACL EMNLP | [Link](https://aclanthology.org/D17-1045/) |
| 2017 | **TernGrad: Ternary gradients to reduce communication in distributed deep learning** | Quantization | NeurIPS | [Link](https://papers.nips.cc/paper_files/paper/2017/hash/89fcd07f20b6785b92134bd6c1d0fa42-Abstract.html) |
| 2017 | **QSGD: Communication-efficient SGD via gradient quantization and encoding** | Quantization | NeurIPS | [Link](https://proceedings.neurips.cc/paper/2017/hash/6c340f25839e6acdc73414517203f5f0-Abstract.html) |

#### 2.2.3 Training Latency Reduction
| Year   | Title |  Category | Venue  | Paper Link  |
|-------|--------|--------|-----------|------------|
| 2020 | **Resource allocation in mobility-aware federated learning networks: A deep reinforcement learning approach** | Load balancing | IEEE WF-IoT | [Link](https://ieeexplore.ieee.org/document/9221089) | 
| 2019 | **Efficient training management for mobile crowd-machine learning: A deep reinforcement learning approach** | Load balancing | IEEE WCL | [Link](https://ieeexplore.ieee.org/document/8716527) |

