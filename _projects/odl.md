---
layout: page
title: On-Device-Learning for MicroControllers
description: Applications and Software for Efficient ODL on MCUs
img: 
importance: 1
category: ongoing
related_publications: NADALINI2023212, nadalini2022pulp, cioflan2022towards, ravaglia2021tinyml, ravaglia2020memory
---

Ultra-low power devices are now powered with on-board processing resources to extract meaninful information from sensor data using Deep Learning models. 
These models are trained using powerfull high-performance machines and then frozen to be deployed on scale on low-power Micro-Controller platforms. 

This line of research tackles the common _train-once-deploy-everywhere_ scheme by investigating if deep learning models can be updated directly on-device after deployment, in short On-Device Leaning (ODL).

## PULPTrain-lib: Bringing ODL to MicroControllers (MCUs)
The library collects deep learning primitives for layer-wise forward and backward passes.
the target platform is the [PULP platform](https://pulp-platform.org/): a MCU-class architecture featuring multiple RISC-V cores with a customized ISA.
Our efficient software solution exploits parallelization, loop unrolling and vectorized MAC instrunctions, with full- and half-precision floating point formats. 
The library is open-source on [GitHub](https://github.com/pulp-platform/pulp-trainlib).

## Continual Learning on MCUs

We formulated a cost model to bring continual learning with [latent replays](https://arxiv.org/abs/1912.01100) on multi-core MCUs. 
To reduce the memory requirement, we proposed to a low-bitwidth quantization for the replay tensors up to 7 bits for a lossless solution {% cite ravaglia2021tinyml, ravaglia2020memory %}. 
Thanks to our system architecture and software stack, we could scale the final accuracy after ODL without forgetting depending on the memory size to store the replay buffer.

