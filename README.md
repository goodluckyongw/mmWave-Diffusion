# mmWave-Diffusion: A Novel Framework for Respiration Sensing Using Observation-Anchored Conditional Diffusion Model

> **🎉 News:** Our paper has been accepted by **ICASSP 2026**! The pre-print version is now available on [arXiv:2603.20700](https://arxiv.org/abs/2603.20700).

## 📖 Introduction

This repository contains the official core diffusion framework and the Radar Diffusion Transformer (RDT) implementation from our paper. 

**mmWave-Diffusion** is designed for fine-grained, contactless human respiratory monitoring using millimeter-wave (mmWave) radar. While mmWave radar offers a promising non-invasive sensing solution, extracting clean respiratory signals is highly challenging due to nonstationary interference from body micromotions. This project provides a robust, generative approach to denoise and reconstruct high-fidelity respiratory waveforms directly from radar phase observations.

## 📄 Abstract

Millimeter-wave (mmWave) radar enables contactless respiratory sensing, yet fine-grained monitoring is often degraded by nonstationary interference from body micromotions. To achieve micromotion interference removal, we propose mmWave-Diffusion, an observation-anchored conditional diffusion framework that directly models the residual between radar phase observations and the respiratory ground truth, and initializes sampling within an observation-consistent neighborhood rather than from Gaussian noise—thereby aligning the generative process with the measurement physics and reducing inference overhead. The accompanying Radar Diffusion Transformer (RDT) is explicitly conditioned on phase observations, enforces strict one-to-one temporal alignment via patch-level dual positional encodings, and injects local physical priors through banded-mask multi-head cross-attention, enabling robust denoising and interference removal in just 20 reverse steps. Evaluated on 13.25 hours of synchronized radar-respiration data, mmWave-Diffusion achieves state-of-the-art waveform reconstruction and respiratory-rate estimation with strong generalization.

## 📂 Repository Structure

- `basic_ops.py`         # Utility layers: SiLU, GroupNorm32, timestep embeddings
- `gaussian_diffusion.py`# Diffusion forward / backward / training / sampling
- `respace.py`           # SpacedDiffusion: step-skipping wrapper for fast sampling
- `script_util.py`       # Helper to create diffusion instances
- `network.py`           # Radar Diffusion Transformer (RDT)

# 📌 Citation
If you find this code or our paper useful for your research, please consider citing our work:
@inproceedings{wang2026mmwavediffusion,
  title={mmWave-Diffusion: A Novel Framework for Respiration Sensing Using Observation-Anchored Conditional Diffusion Model},
  author={Yong Wang, Qifan Shen, Bao Zhang, Zijun Huang, Chengbo Zhu, Shuai Yao, Qisong Wu}, 
  booktitle={ICASSP 2026 - 2026 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  year={2026},
  organization={IEEE}
}
