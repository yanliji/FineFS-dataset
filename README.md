# Fine Figure Skating (FineFS) Dataset

We collect a large-scale **Fine-grained Figure Skating dataset (FineFS)** involving RGB videos and estimated skeleton data, providing rich annotations for multiple downstream action analysis tasks. There are 1167 skating samples in our proposed FineFS dataset, annotated with fine-grained score labels, technical subaction category labels from coarse to fine, as well as the start and end time of technical subactions.

****

## 1. Overview

There are 1167 skating samples in our proposed FineFS dataset: 729 samples from the short program and 438 samples from free skating; 570 samples are from male athletes and 597 samples are from female athletes. The dataset is separated into a training set and a test set with 933 and 234 samples, respectively. Video length is around 2min40s for the short program and 4min for free skating. The frame rate is 25 frame/second in videos. Table. 1 clearly exhibits the statistics of our dataset.

<div align=center><b>Table 1: Statistics of the FineFS dataset. M means male and F means female.</b></div>

<table>
  <tr>
    <th></th>
    <th>Number of Samples</th>
    <th>Duration</th>
    <th>Train:Test</th>
    <th>File Number</th>
  </tr>
  <tr>
    <td>Short Program</td>
    <td>729 (350 M, 379 F)</td>
    <td>2min40s±</td>
    <td>583:146</td>
    <td>0-728</td>
  </tr>
  <tr>
    <td>Free Skating</td>
    <td>438 (220 M, 218 F)</td>
    <td>4min±</td>
    <td>350:88</td>
    <td>729-1166</td>
  </tr>
</table>


Fig. 1 exhibits two sample sequences belonging to short program (the top row, 7 technical element actions) and free skating (the bottom row, 12 technical element actions), respectively. Each sample involves two modalities (RGB videos and 2D/3D skeleton sequences). The FineFS is annotated with fine-grained score labels, technical subaction category labels from coarse to fine, as well as the start and end time of technical subactions.

<div align=center><img width="800" height="240" src="./imgs/DatasetFigureNew.png"/></div>

<div align=center><b>Figure 1: Sample visualization for the FineFS dataset.</b></div>

****

## 2. Data Structure and Download

Our proposed dataset is stored in the following directory:

```haskell
.
├── data
│   ├── annotation
│       ├── 0.json
│       ├── 1.json
│       ├── …
│       └── 1166.json
│   ├── skeleton
│       ├── 0.npz
│       ├── 1.npz
│       ├── …
│       └── 1166.npz
│   ├── video
│       ├── 0.mp4
│       ├── 1.mp4
│       ├── …
│       └── 1166.mp4
│   └── video_features
│       ├── 0.pkl
│       ├── 1.pkl
│       ├── …
│       └── 1166.pkl
...
```

All files are numbered 0-1166, where 0-728 is for the short program and 729-1166 is for free skating.

- **annotation (1167 `.json` files with the size of 3.75MB)**: The FineFS is annotated in `.json` files with fine-grained score labels, technical subaction category labels from coarse to fine, as well as the start and end time of technical subactions. Please refer to `Appendix.pdf` Tab. 3 for the item description and example in the annotation file for one sample. Annotation `.json` files are stored in the `data/annotation` directory.
- **video (1167 `.mp4` files with the size of 46.3GB)**: We cut full competition videos into video samples that contain a single athlete performing a short program or a free skating item from the start of the competition music to the end. Video `.mp4` files are stored in the `data/video` directory.
- **video features (1167 `.pkl` files with the size of 955MB)**: We provide video features extracted by VST pretrained on the Kinetics-600 dataset for your convenience. Video features `.pkl` files are stored in the `data/video_features` directory.
- **skeleton (1167 `.npz` files with the size of 828MB)**: We extract 3D skeleton joints following athletes’ actions in videos, and perform postprocessing for further rectification of the skeleton sequences. Each skeleton frame has 17 joints described in camera space coordinates. Skeleton `.npz` files are stored in the `data/skeleton` directory.

We have made the full dataset available on [[Baidu Drive]](https://pan.baidu.com/s/1ihV47FIgNhATm5g1XTcaNg) (extract number: hri6) and [[Google Drive]]().

****

## 3. Citation
@inproceedings{JI2023FineFS,
  title={Localization-assisted Uncertainty Score Disentanglement Network for Action Quality Assessment},
  author={Yanli Ji and Lingfeng Ye and Huili Huang and Lijing Mao and Yang Zhou and Lingling Gao}
  booktitle={ACM MM},
  pages={1--10},
  year={2023}}


## What's more
Please refer to the file `Appendix.pdf` for more details. If you have any questions about this dataset including wishing to evaluate your algorithm on this dataset, feel free to contact us. 
