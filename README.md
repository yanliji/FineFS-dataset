# UESTC Fine Figure Skating (FineFS) Dataset

We collect a large-scale **Fine-grained Figure Skating dataset (FineFS)** involving RGB videos and estimated skeleton data, providing rich annotations for multiple downstream action analysis tasks. There are 1167 skating samples in our proposed FineFS dataset, annotated with fine-grained score labels, technical subaction category labels from coarse to fine, as well as the start and end time of technical subactions.

****

## 1. Overview

There are 1167 skating samples in our proposed FineFS dataset: 729 samples from short program and 438 samples from free skating; 570 samples are from male athletes and 597 samples are from female athletes. We split the dataset into training set and test set with 933 and 234 samples, respectively. Video length is around 2min40s for short program and 4min for free skating. The frame rate of videos is 25 frame/second. Tab. 1 clearly exhibits the statistics of our dataset.

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

All files are numbered 0-1166, where 0-728 is for short program and 729-1166 is for free skating.

- **annotation (1167 `.json` files with size of 3.75MB)**: The FineFS is annotated in `.json` files with fine-grained score labels, technical subaction category labels from coarse to fine, as well as the start and end time of technical subactions. Please refer to `Appendix.pdf` Tab. 3 for item description and example in the annotation file for one sample. Annotation `.json` files are stored in the `data/annotation` directory.
- **video (1167 `.mp4` files with size of 46.3GB)**: We cut full competition videos into video samples which contains a single athlete performing a short program or a free skating item from the start of the competition music to the end. Video `.mp4` files are stored in the `data/video` directory.
- **video features (1167 `.pkl` files with size of 955MB)**: We provide video features extracted by VST pretrained on the Kinetics-600 dataset for your convenience. Video features `.pkl` files are stored in the `data/video_features` directory.
- **skeleton (1167 `.npz` files with size of 829MB)**: We extract 3D skeleton joints following athletes’ action in videos, and perform postprocessing for a further rectification on the skeleton sequences. Each skeleton frame has 17 joints described in camera space coordinate. Skeleton `.npz` files are stored in the `data/skeleton` directory.

We have made the full dataset available on [[Baidu Drive]]() (extract number: hri6) and [[Google Drive]]().

****

## What's more

Please refer to the file `Appendix.pdf` for more details. If you have any questions about this dataset including wishing to evalute your algorithm on this dataset, feel free to contact us with e-mail [yanliji@uestc.edu.cn](yanliji@uestc.edu.cn). 
