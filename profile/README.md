# Research Proposal

## Team formation

- [2024-20157 김해람](https://github.com/haeramkeem)
- [2024-29162 박준엽](https://github.com/junyupp)
- [2023-22811 하지원](https://github.com/Jiwon46)

## The motivation and the goal of your work

- Implementing FDP (Flexible Data Placement), the latest host-guided data placement method, into NVMeVirt with the characteristics of real devices enables testing and gaining insights into its functionality, leading to research on better utilization of FDP features.

## The problem you would like to solve

- FDP is the latest technology capable of addressing the limitations of existing technologies (e.g., Multi-stream, ZNS). However, finding testable devices is not easy at this point, and even if one can, they only implement limited functionalities. Furthermore, existing emulators (e.g. QEMU) for this technology differ from real devices in a performance perspective.

## Brief summary of related work

- [Multi-stream SSDs](https://www.usenix.org/system/files/conference/hotstorage14/hotstorage14-paper-kang.pdf) are a type of SSD that manage multiple independent data streams to optimize performance and lifespan. [Zoned Namespace SSDs](https://www.usenix.org/system/files/atc21-bjorling.pdf) operate by dividing the address space into zones to facilitate efficient data placement and management.
- Sang-hoon Kim et al. proposes [NVMeVirt](https://www.usenix.org/system/files/fast23-kim.pdf) that introduces a software-defined approach to NVMe devices, bridging the gap between host I/O stack and virtual devices, supporting various storage configurations and facilitating storage research.
- Joshi K et al. implemented [I/O Passthru](https://www.usenix.org/system/files/fast24-joshi.pdf), utilized in the mainline Linux Kernel, leverages NVMe char interface and io_uring to boost adoption of new NVMe technologies such as FDP.

## Your ideas to solve the problem

- Modify NVMeVirt to enable FDP feature utilization and implement an emulation device on NVMeVirt that reflects the characteristics (bandwidth, latency, etc.) of the actual device (Samsung FDP SSD).

## Research plan for the project

- Background research
  - FDP feature and related work study
  - NVMeVirt code review
- Implementation
  - FDP compatible NVMe write command implementation on NVMeVirt
  - Performance emulation parameter (e.g. bandwidth, latency) customization based on Samsung FDP SSD
- Evaluation
  - Benchmark (e.g. FIO, Cachelib) comparison with real device (Samsung FDP SSD)
  - Show measurements of workloads with combinations of write sequence, data hotness, and the number of RUH used in FDP
