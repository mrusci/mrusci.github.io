---
layout: page
title: Audio-Visual Inference on MCU-powered devices
description: System-level integration of audio-visual algorithms on MicroControllers 
img: 
importance: 1
category: ongoing
related_publications: lamberti2023bio, rusci2022accelerating, fariselli2021integer, lamberti2021low, 
---

This project aims at realizing innovative smart sensor solutions in the audio-visual space by bringing modern deep-learning algorithms on MCUs. 
Our system-level design involves the sensing and processing subsystems and the tests regard public datasets and real-wold data. 


## Audio Denoiser

Our Speech Enhancement (SE) solution is based on a Recurrent Neural Network (RNN) and targets a state-of-the-art MicroController Unit (MCU), with 1+8 general-purpose RISC-V cores. 
To achieve low-latency execution, we propose an optimized software pipeline interleaving parallel computation of LSTM or GRU recurrent blocks, featuring vectorized 8-bit integer (INT8) and 16-bit floating-point (FP16) compute units, with manually-managed memory transfers of model parameters. 
To ensure minimal accuracy degradation with respect to the full-precision models, we propose a novel FP16-INT8 Mixed-Precision Post-Training Quantization (PTQ) scheme that compresses the recurrent layers to 8-bit while the bit precision of remaining layers is kept to FP16. 
Experiments are conducted on multiple LSTM and GRU based SE models trained on the Valentini dataset, featuring up to 1.24M parameters. 
Thanks to the proposed approaches, we speed-up the computation by up to 4x with respect to the lossless FP16 baselines. 
Differently from a uniform 8-bit quantization that degrades the PESQ score by 0.3 on average, the Mixed-Precision PTQ scheme leads to a low-degradation of only 0.06, while achieving a 1.4–1.7x memory saving. 
Thanks to this compression, we cut the power cost of the external memory by fitting the large models on the limited on-chip non-volatile memory and we gain a MCU power saving of up to 2.5x by reducing the supply voltage from 0.8V to 0.65V while still matching the real-time constraints. 
Our design results >10x more energy efficient than state-of-the-art SE solutions deployed on single-core MCUs that make use of smaller models and quantization-aware training.

## Visual Object Detection

We unlock single-shot Visual Object detection on multi-core MCUs for licence plate recognition or nano-drone robotic application. 
In particular, we fine-tuned SSD-MobileNet with application specific data taken from the sensor and we applied 8-bit quantization using QAT. 
The model can run on the 8-core GAP8 microcontroller running at 1.6 frame/s. 

