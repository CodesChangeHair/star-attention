# Star Operation in Self-Attention for 3D Human Pose Estimation

This repository contains the official implementation of our paper:

> **Star Operation in Self-Attention for 3D Human Pose Estimation**  
> Hao Wang, Xiaochuan Wang, Ruijun Liu, Xiaoming Chen, Haisheng Li  
> Beijing Technology and Business University, Beihang University  
> *Submitted/Published in [ICASSP 2025](https://ieeexplore.ieee.org/document/10889693)*

## ✨ Highlights

- ✅ We propose **Star-Attention**, which enhances traditional self-attention by incorporating **element-wise interactions**.
- ✅ Star-Attention captures hierarchical features, reducing jitter in 3D pose predictions.
- ✅ The module is easy to integrate into Transformer-based baselines like **MixSTE**.

## Methods

* (a): Attention module
* (b): Star-Attention module

![StarAttention](https://github.com/user-attachments/assets/de5864ed-ed39-4d01-98af-524673582ba5)


## How to Use

Prepare Environment and Dataset according to [MixSTE](https://github.com/JinluZhang1126/MixSTE/tree/main). 

Replace `model_cross.py` by our `model_cross_atten_star.py`: `cp model_cross_atten_star.py common/model_cross.py`.

Evaluation and Training is same as MixSTE.

## 🔧 Core Code

### Define `Wa`

```
  if (self.mode == 'spatial'):
      self.Wa =  nn.Parameter(torch.ones(num_joints, head_dim))
  elif (self.mode == 'temporal'):
      self.Wa = nn.Parameter(torch.ones(num_frames, head_dim))
  torch.nn.init.kaiming_normal_(self.Wa, a=0, mode='fan_in', nonlinearity='relu')
```

### Star-Attention

```
  if (self.mode == 'spatial'):
      attn = (self.Wa @ (q * k).transpose(-2, -1) + (q @ k.transpose(-2, -1)) * self.scale) * 0.5
  elif (self.mode == 'temporal'):
      attn = (self.Wa @ (q * k).transpose(-2, -1)  + (q @ k.transpose(-2, -1)) * self.scale) * 0.5
```

##  Citation
@article{wang2025starattention,
  title={Star Operation in Self-Attention for 3D Human Pose Estimation},
  author={Wang, Hao and Wang, Xiaochuan and Liu, Ruijun and Chen, Xiaoming and Li, Haisheng},
  year={2025},
  journal={[ICASSP 2025]}
}

## Contact 

Corresponding Author: Xiaochuan Wang (wangxc@btbu.edu.cn)
