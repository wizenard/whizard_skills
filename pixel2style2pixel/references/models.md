# pSp Pretrained Models Reference

## Main Models

| Task | Dataset | Resolution | Download |
|------|---------|------------|----------|
| StyleGAN Inversion | FFHQ | 1024x1024 | [Link](https://drive.google.com/file/d/1bMTNWkh5LArlaWSc_wa8VKyq2V42T2z0/view) |
| Face Frontalization | FFHQ | 1024x1024 | [Link](https://drive.google.com/file/d/1_S4THAzXb-97DbpXmanjHtXRyKxqjARv/view) |
| Sketch to Image | CelebA-HQ | 1024x1024 | [Link](https://drive.google.com/file/d/1lB7wk7MwtdxL-LL4Z_T76DuCfk00aSXA/view) |
| Segmentation to Image | CelebAMask-HQ | 1024x1024 | [Link](https://drive.google.com/file/d/1VpEKc6E6yG3xhYuZ0cq8D2_1CbT0Dstz/view) |
| Super Resolution | CelebA-HQ | 1024x1024 | [Link](https://drive.google.com/file/d/1ZpmSXBpJ9pFEov6-jjQstAlfYbkebECu/view) |
| Toonify | FFHQ | 1024x1024 | [Link](https://drive.google.com/file/d/1YKoiVuFaqdvzDP5CZaqa3k5phL-VDmyz/view) |

## Auxiliary Models (for training)

| Model | Purpose | Download |
|-------|---------|----------|
| FFHQ StyleGAN | Pretrained generator | [Link](https://drive.google.com/file/d/1EM87UquaoQmk17Q8d5kYIAHqu0dkYqdT/view) |
| IR-SE50 | ID loss (face) | [Link](https://drive.google.com/file/d/1KW7bjndL3QG3sxBbZxreGHigcCCpsDgn/view) |
| MoCo ResNet-50 | Similarity loss (non-face) | [Link](https://drive.google.com/file/d/18rLcNGdteX5LwT7sv_F7HWr12HpVEzVe/view) |
| CurricularFace | ID metric | [Link](https://drive.google.com/file/d/1f4IwVa2-Bn9vWLwB-bUwm53U_MlvinAj/view) |
| MTCNN | Face detection | [Link](https://drive.google.com/file/d/1tJ7ih-wbCO6zc3JhI_1ZGjmwXKKaPlja/view) |

## Training Configs by Task

### StyleGAN Inversion
```bash
--dataset_type=ffhq_encode
--lpips_lambda=0.8 --l2_lambda=1 --id_lambda=0.1
```

### Face Frontalization
```bash
--dataset_type=ffhq_frontalize
--lpips_lambda=0.08 --l2_lambda=0.001
--lpips_lambda_crop=0.8 --l2_lambda_crop=0.01
--id_lambda=1 --w_norm_lambda=0.005
```

### Sketch to Face
```bash
--dataset_type=celebs_sketch_to_face
--label_nc=1 --input_nc=1
--lpips_lambda=0.8 --l2_lambda=1 --id_lambda=0
--w_norm_lambda=0.005
```

### Segmentation to Face
```bash
--dataset_type=celebs_seg_to_face
--label_nc=19 --input_nc=19
--lpips_lambda=0.8 --l2_lambda=1 --id_lambda=0
--w_norm_lambda=0.005
```

### Super Resolution
```bash
--dataset_type=celebs_super_resolution
--resize_factors=1,2,4,8,16,32
--lpips_lambda=0.8 --l2_lambda=1 --id_lambda=0.1
--w_norm_lambda=0.005
```

### Toonify
```bash
--dataset_type=ffhq_encode
--stylegan_weights=/path/to/toonify_generator.pth
--lpips_lambda=0.8 --l2_lambda=1 --id_lambda=1
--w_norm_lambda=0.025 --max_steps=6000
```
