---
license: apache-2.0
tags:
  - keypoints
  - motion
  - anny
  - soma
  - kimodo
  - rfd-1173
  - rfd-2203
configs:
  - config_name: subset-01-train
    data_files: "subset-01-*/train.parquet"
  - config_name: subset-01-val
    data_files: "subset-01-*/val.parquet"
---

# datasource-anny-soma-corpus

A keypoint corpus of rendered ANNY body frames, published as Parquet subsets that each carry a manifest.

## What it is for

Training keypoint models on constructed renders. Each row pairs a rendered frame with its camera, the posed body vertices, baked 2D keypoints and the pose that drove it, and each subset's manifest records its motion source and synthetic class. [RFD 2203](https://github.com/V-Sekai-fire/manuals-weftspun/blob/main/rfd/2203-anny-soma-first-subset-corpus-shape.exs) owns the row shape and the publishing rules.

## Check a subset

    python check_corpus_manifest.py --help

The gate checks a rendered subset against RFD 2203 before it is published, and carries negative controls for its own rules.

## Licence

Apache-2.0. See [LICENSE](LICENSE); `CITATION.cff` records each upstream the corpus draws on.
