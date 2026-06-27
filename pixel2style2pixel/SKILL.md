---
name: pixel2style2pixel
description: >
  Use the pixel2style2pixel (pSp) framework for image-to-image translation tasks using
  StyleGAN encoders. Use when: (1) Inverting real images into StyleGAN latent space,
  (2) Face frontalization from arbitrary angles, (3) Conditional image synthesis from
  sketches or segmentation maps, (4) Super-resolution up to x32, (5) Image style transfer
  and cartoonization (Toonify), (6) Any task requiring mapping images to StyleGAN's W+
  latent space for manipulation. Trigger on requests about StyleGAN encoding, image
  translation, face manipulation, super-resolution, or GAN-based image processing.
---

# pixel2style2pixel (pSp) Skill

Use the pSp framework for image-to-image translation via StyleGAN encoding. CVPR 2021 official implementation.

## Overview

pSp trains an encoder that directly maps input images to StyleGAN's W+ latent space, enabling image-to-image translation without the traditional "invert first, edit later" approach. No adversarial training required.

## Supported Tasks

| Task | Dataset | Key Flags |
|------|---------|-----------|
| StyleGAN Inversion | FFHQ | `--dataset_type=ffhq_encode` |
| Face Frontalization | FFHQ | `--dataset_type=ffhq_frontalize` |
| Sketch to Face | CelebA-HQ | `--dataset_type=celebs_sketch_to_face` |
| Segmentation to Face | CelebAMask-HQ | `--dataset_type=celebs_seg_to_face` |
| Super Resolution | CelebA-HQ | `--dataset_type=celebs_super_resolution` |
| Toonify | FFHQ | Custom StyleGAN weights |

## Installation

```bash
git clone https://github.com/eladrich/pixel2style2pixel.git
cd pixel2style2pixel

# Create conda environment
conda env create -f environment/psp_env.yaml
conda activate psp
```

## Prerequisites

- Linux or macOS
- NVIDIA GPU + CUDA CuDNN
- Python 2.3

## Quick Start (Colab)

Open `notebooks/inference_playground.ipynb` in Colab — auto-downloads pretrained models and runs inference.

## Pretrained Models

| Model | Description |
|-------|-------------|
| [StyleGAN Inversion](https://drive.google.com/file/d/1bMTNWkh5LArlaWSc_wa8VKyq2V42T2z0/view) | FFHQ encoding |
| [Face Frontalization](https://drive.google.com/file/d/1_S4THAzXb-97DbpXmanjHtXRyKxqjARv/view) | Front-facing faces |
| [Sketch to Image](https://drive.google.com/file/d/1lB7wk7MwtdxL-LL4Z_T76DuCfk00aSXA/view) | Sketch synthesis |
| [Segmentation to Image](https://drive.google.com/file/d/1VpEKc6E6yG3xhYuZ0cq8D2_1CbT0Dstz/view) | Segmentation synthesis |
| [Super Resolution](https://drive.google.com/file/d/1ZpmSXBpJ9pFEov6-jjQstAlfYbkebECu/view) | Up to x32 |
| [Toonify](https://drive.google.com/file/d/1YKoiVuFaqdvzDP5CZaqa3k5phL-VDmyz/view) | Cartoon style |

## Training

### Basic Training Command

```bash
python scripts/train.py \
  --dataset_type=ffhq_encode \
  --exp_dir=/path/to/experiment \
  --encoder_type=GradualStyleEncoder \
  --start_from_latent_avg \
  --lpips_lambda=0.8 \
  --l2_lambda=1 \
  --id_lambda=0.1
```

### Task-Specific Training

**Face Frontalization:**
```bash
python scripts/train.py \
  --dataset_type=ffhq_frontalize \
  --lpips_lambda=0.08 --l2_lambda=0.001 \
  --lpips_lambda_crop=0.8 --l2_lambda_crop=0.01 \
  --id_lambda=1 --w_norm_lambda=0.005
```

**Sketch to Face:**
```bash
python scripts/train.py \
  --dataset_type=celebs_sketch_to_face \
  --label_nc=1 --input_nc=1 \
  --id_lambda=0
```

**Segmentation to Face:**
```bash
python scripts/train.py \
  --dataset_type=celebs_seg_to_face \
  --label_nc=19 --input_nc=19 \
  --id_lambda=0
```

**Super Resolution:**
```bash
python scripts/train.py \
  --dataset_type=celebs_super_resolution \
  --resize_factors=1,2,4,8,16,32
```

## Inference

```bash
python scripts/inference.py \
  --exp_dir=/path/to/experiment \
  --checkpoint_path=experiment/checkpoints/best_model.pt \
  --data_path=/path/to/test_data \
  --couple_outputs
```

## Multi-Modal Synthesis

```bash
python scripts/style_mixing.py \
  --exp_dir=/path/to/experiment \
  --checkpoint_path=/path/to/experiment/checkpoints/best_model.pt \
  --data_path=/path/to/test_data/ \
  --n_images=25 \
  --n_outputs_to_generate=5 \
  --latent_mask=8,9,10,11,12,13,14,15,16,17
```

## Key Flags

| Flag | Description |
|------|-------------|
| `--output_size` | StyleGAN resolution (256/512/1024) |
| `--encoder_type` | Use `GradualStyleEncoder` |
| `--start_from_latent_avg` | Initialize from latent average |
| `--id_lambda` | Identity loss weight (face tasks) |
| `--moco_lambda` | MoCo similarity loss (non-face tasks) |
| `--lpips_lambda` | Perceptual loss weight |
| `--l2_lambda` | L2 reconstruction loss weight |
| `--w_norm_lambda` | W+ regularization weight |
| `--use_wandb` | Enable Weights & Biases logging |

## Identity Loss Options

- **Face domain**: Use `--id_lambda` (ArcFace-based)
- **Non-face domain**: Use `--moco_lambda=0.5` (MoCo ResNet-based)
- Cannot use both simultaneously

## Resources

- Paper: https://arxiv.org/abs/2008.00951
- GitHub: https://github.com/eladrich/pixel2style2pixel
- Demo: https://replicate.ai/eladrich/pixel2style2pixel
- Colab: http://colab.research.google.com/github/eladrich/pixel2style2pixel/blob/master/notebooks/inference_playground.ipynb
