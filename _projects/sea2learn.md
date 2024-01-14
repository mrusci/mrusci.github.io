---
layout: page
title: SEA2Learn (MSCA)
description: Self-Adaptive and Automated Learning Framework for Smart Sensors
img: 
importance: 1
category: ongoing
related_publications: rusci2023device, rusci_interspeech23, 
---

Smart Sensors are key components for the upcoming Green and Digital European era. Recently, novel emerging electronics components – such as high energy-efficient many-core application processors featuring a power consumption of few tens of mWs – have enabled high-accurate on-device inference capabilities, i.e. Deep Learning inference, to extract high-level information from sensor data. However, this technology improvement is not sufficient to ensure robust solutions suitable for consumer and industrial applications. The main issue comes from the wide variety in real-world test conditions and, consequently, the lack at design-time of representative (labelled) sensor data, needed to train DL inference networks. For this reason, the currently used “train-once-and-deploy-everywhere” design process for edge intelligence has proved to be weak, even after an endless cyclic procedure involving data collection, model training and in-field testing.

This limitation is addressed by the SEA2Learn project, funded by the [Horizon Europe MSCA program](https://cordis.europa.eu/project/id/101067475), by developing energy-efficient and real-time mechanisms to adapt the inference capabilities of resource-constrained smart sensors based on the stimulus from the surrounding environment. The proposed strategy, which is unprecedent in this domain, aims at placing in the same training loop multiple smart sensor nodes that interact with a Learning Agent. The latter will leverage a new class of lightweight methods belonging to the Continual Learning (CL) domain operating on unlabelled multi-sensor data. Thanks to the envisioned SEA2Learn framework, the embedded intelligence can adapt over time based on real-world data, making the design process more robust and 10-100x faster than today. 

## Main Project Results:

* In our recent works, we study a KWS solution for microcontrollers where the target keyword class is initialized using _few-examples_ recorded from the user in-the-field.
Our study concluded that training a KWS encoder with triplet loss on a large dataset led to superior accuracy in a realistic open-set settings with respect to precedent methods based on prototypical loss {% cite rusci_interspeech23 %}. 
When tested on multiple KWS tiny models, we report an accuracy of up to 80% on the Google Speech Command dataset using only 10 examples of utterances not seen during training {% cite rusci2023device %}. 
On a multicore microcontroller with a power envelope of 25 mW, the most accurate ResNet15 model takes 9.7 ms to process a 1-s speech frame, demonstrating the feasibility of on-device KWS customization for tiny devices without requiring any backpropagation-based transfer learning.
