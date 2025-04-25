# Star Operation in Self-Attention for 3D Human Pose Estimation

This repository contains the official implementation of our paper:

> **Star Operation in Self-Attention for 3D Human Pose Estimation**  
> Hao Wang, Xiaochuan Wang, Ruijun Liu, Xiaoming Chen, Haisheng Li  
> Beijing Technology and Business University, Beihang University  
> *Submitted/Published in [ICASSP]*

## ✨ Highlights

- ✅ We propose **Star-Attention**, which enhances traditional self-attention by incorporating **element-wise interactions**.
- ✅ Star-Attention captures hierarchical features, reducing jitter in 3D pose predictions.
- ✅ The module is easy to integrate into Transformer-based baselines like **MixSTE**.

## 代码使用方式

Prepare Environment and Dataset according to MixSTE[MixSTE](https://github.com/JinluZhang1126/MixSTE/tree/main). 

Replace `model_cross.py` by our `model_cross_atten_star.py`: `cp model_cross_atten_star.py common/model_cross.py`.

Evaluation and Training is same as MixSTE.

##  Citation
@article{wang2025starattention,
  title={Star Operation in Self-Attention for 3D Human Pose Estimation},
  author={Wang, Hao and Wang, Xiaochuan and Liu, Ruijun and Chen, Xiaoming and Li, Haisheng},
  year={2025},
  journal={[Your Target Journal or Conference]}
}

## Contact 

Corresponding Author: Xiaochuan Wang (wangxc@btbu.edu.cn)
