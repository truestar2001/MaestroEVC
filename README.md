# Maestro-EVC: Controllable Emotional Voice Conversion Guided by References and Explicit Prosody

[![arXiv](https://img.shields.io/badge/arXiv-2508.06890-B31B1B.svg)](https://arxiv.org/abs/2508.06890)
[![Conference](https://img.shields.io/badge/Accepted%20at-ASRU%202025-blue)](https://2025.ieeeasru.org/)

Demo Page: https://maestroevc.github.io/demo/

This repository contains the official implementation for our paper, **"Maestro-EVC: Controllable Emotional Voice Conversion Guided by References and Explicit Prosody."**

Maestro-EVC is a controllable Emotional Voice Conversion (EVC) framework that enables the independent control of content, speaker identity, and emotional style by effectively disentangling each attribute from separate references, leading to high-quality and emotionally expressive speech synthesis.

## Abstract

Emotional voice conversion (EVC) aims to modify the emotional style of speech while preserving its linguistic content. In practical EVC, controllability, the ability to independently control speaker identity and emotional style using distinct references, is crucial. However, existing methods often struggle to fully disentangle these attributes and lack the ability to model fine-grained emotional expressions such as temporal dynamics. We propose Maestro-EVC, a controllable EVC framework that enables independent control of content, speaker identity, and emotion by effectively disentangling each attribute from separate references. We further introduce a temporal emotion representation and an explicit prosody modeling with prosody augmentation to robustly capture and transfer the temporal dynamics of the target emotion, even under prosody-mismatched conditions. Experimental results confirm that Maestro-EVC achieves high-quality, controllable, and emotionally expressive speech synthesis.

## Prerequisites

* Python 3.11.14

## Setup and Installation

```bash
git clone https://github.com/truestar2001/Maestro_EVC_for_Gaudio
cd Maestro_EVC_for_Gaudio
conda create -n mevc python=3.11
conda activate mevc
pip install -r requirements.txt
mkdir -p checkpoint data inference/output
```

## Extract features
```bash
python extractors/f0.py
python extractors/energy.py
python extractors/hubert.py
python extractors/emotion_diarization_embedding.py
python extractors/speaker_embedding.py
```
## Make inference pairs

- make pairs.txt in folder 'inference'

- pairs.txt must be formatted as:

```bash
<content wav url>|<speaker wav url>|<emotion wav url>
```
## Training
```bash
python train.py
```

## Inference
```bash
python inference.py
```
