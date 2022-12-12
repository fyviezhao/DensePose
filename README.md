# DensePose in Detectron2

DensePose aims at learning and establishing dense correspondences between image pixels
and 3D object geometry for deformable objects, such as humans or animals.
In this repository, we provide the code to train and evaluate DensePose R-CNN and
various tools to visualize DensePose annotations and results.

There are two main paradigms that are used within DensePose project.

## [Chart-based Dense Pose Estimation for Humans and Animals](doc/DENSEPOSE_IUV.md)

<div align="center">
  <img src="https://dl.fbaipublicfiles.com/densepose/web/densepose_teaser_compressed_25.gif" width="700px" />
</div>

For chart-based estimation, 3D object mesh is split into charts and
for each pixel the model estimates chart index `I` and local chart coordinates `(U, V)`.
Please follow the link above to find a [detailed overview](doc/DENSEPOSE_IUV.md#Overview)
of the method, links to trained models along with their performance evaluation in the
[Model Zoo](doc/DENSEPOSE_IUV.md#ModelZoo) and
[references](doc/DENSEPOSE_IUV.md#References) to the corresponding papers.

## [Continuous Surface Embeddings for Dense Pose Estimation for Humans and Animals](doc/DENSEPOSE_CSE.md)

<div align="center">
  <img src="https://dl.fbaipublicfiles.com/densepose/web/densepose_cse_teaser.png" width="700px" />
</div>

To establish continuous surface embeddings, the model simultaneously learns
descriptors for mesh vertices and for image pixels.
The embeddings are put into correspondence, thus the location
of each pixel on the 3D model is derived.
Please follow the link above to find a [detailed overview](doc/DENSEPOSE_CSE.md#Overview)
of the method, links to trained models along with their performance evaluation in the
[Model Zoo](doc/DENSEPOSE_CSE.md#ModelZoo) and
[references](doc/DENSEPOSE_CSE.md#References) to the corresponding papers.

# Installation
If you do not need `import densepose` but rather to simply use densepose's `apply_net.py` offline, you can only install [pre-build detectron2](https://detectron2.readthedocs.io/en/latest/tutorials/install.html#install-pre-built-detectron2-linux-only) package as follow:

```shell
$ conda create -n detectron2 python=3.8
$ conda activate detectron2
$ conda install pytorch==1.10.0 torchvision==0.11.0 torchaudio==0.10.0 cudatoolkit=11.3 -c pytorch -c conda-forge
$ python -m pip install detectron2 -f \
  https://dl.fbaipublicfiles.com/detectron2/wheels/cu113/torch1.10/index.html
$ pip install av scipy opencv-python
```

# Quick Start

See [ Getting Started ](doc/GETTING_STARTED.md)

# Model Zoo

Please check the dedicated pages
for [chart-based model zoo](doc/DENSEPOSE_IUV.md#ModelZoo)
and for [continuous surface embeddings model zoo](doc/DENSEPOSE_CSE.md#ModelZoo).

# What's New

* June 2021: [DensePose CSE with Cycle Losses](doc/RELEASE_2021_06.md)
* March 2021: [DensePose CSE (a framework to extend DensePose to various categories using 3D models)
  and DensePose Evolution (a framework to bootstrap DensePose on unlabeled data) released](doc/RELEASE_2021_03.md)
* April 2020: [DensePose Confidence Estimation and Model Zoo Improvements](doc/RELEASE_2020_04.md)

# License

Detectron2 is released under the [Apache 2.0 license](../../LICENSE)

## <a name="CitingDensePose"></a>Citing DensePose

If you use DensePose, please refer to the BibTeX entries
for [chart-based models](doc/DENSEPOSE_IUV.md#References)
and for [continuous surface embeddings](doc/DENSEPOSE_CSE.md#References).

