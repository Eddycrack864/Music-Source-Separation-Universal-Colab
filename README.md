# Music-Source-Separation-Universal-Colab

Repository for training models for music source separation. Repository is based on [kuielab code](https://github.com/kuielab/sdx23/tree/mdx_AB/my_submission/src) for [SDX23 challenge](https://github.com/kuielab/sdx23/tree/mdx_AB/my_submission/src). The main idea of this repository is to create training code, which is easy to modify for experiments. Brought to you by [MVSep.com](https://mvsep.com).

Repository by: [ZFTurbo](https://github.com/ZFTurbo)
Colab by: [Not Eddy (Spanish Mod)](http://discord.com/users/274566299349155851) on [AI HUB](https://discord.gg/aihub)

# Models

Model can be chosen with `--model_type` arg.

Available models:
* MDX23C based on [KUIELab TFC TDF v3 architecture](https://github.com/kuielab/sdx23/). Key: `mdx23c`.
* Demucs4HT [[Paper](https://arxiv.org/abs/2211.08553)]. Key: `htdemucs`.
* VitLarge23 based on [Segmentation Models Pytorch](https://github.com/qubvel/segmentation_models.pytorch). Key: `segm_models`. 
* Mel-Band RoFormer [[Paper](https://arxiv.org/abs/2310.01809), [Repository](https://github.com/lucidrains/BS-RoFormer)]. Key: `mel_band_roformer`.
* Swin Upernet [[Paper](https://arxiv.org/abs/2103.14030)] Key: `swin_upernet`.
* BandIt Plus [[Paper](https://arxiv.org/abs/2309.02539), [Repository](https://github.com/karnwatcharasupat/bandit)] Key: `bandit`.


# Vocal models
| Model Type | Instruments | Metrics (SDR) |
|:-------------:|:-------------:|:-----:|
| MDX23C | vocals / other | SDR vocals: 10.17 |
| HT Demucs | vocals / other | SDR vocals: 8.78 |
| Segm Models (VitLarge23) | vocals / other | SDR vocals: 9.77 |
| Mel Band RoFormer | vocals (*) / other | SDR vocals: 8.42 |
| Swin Upernet | vocals / other | SDR vocals: 7.57 |

**Note**: Metrics measured on [Multisong Dataset](https://mvsep.com/en/quality_checker).

# Multi-stem models

| Model Type | Instruments | Metrics (SDR) |
|:-------------:|:-------------:|:-----:|
| MDX23C | bass / drums / vocals / other | MUSDB test avg: 7.15 (bass: 5.77, drums: 7.93 vocals: 9.23 other: 5.68) Multisong avg: 7.02 (bass: 8.40, drums: 7.73 vocals: 7.36 other: 4.57) |
| BandIt Plus | speech / music / effects | DnR test avg: 11.50 (speech: 15.64, music: 9.18 effects: 9.69) |

**Note**: Models were trained only on MUSDB18HQ dataset (100 songs train data)

# Citation

* [arxiv paper](https://arxiv.org/abs/2305.07489)

```
@misc{solovyev2023benchmarks,
      title={Benchmarks and leaderboards for sound demixing tasks}, 
      author={Roman Solovyev and Alexander Stempkovskiy and Tatiana Habruseva},
      year={2023},
      eprint={2305.07489},
      archivePrefix={arXiv},
      primaryClass={cs.SD}
}
```
