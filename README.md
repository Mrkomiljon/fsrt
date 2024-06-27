# FSRT: Facial Scene Representation Transformer for Face Reenactment (CVPR 2024)



https://github.com/Mrkomiljon/fsrt/assets/92161283/246752e8-09f9-4da5-bd02-3ac113190485


## Setup
Please complete the following steps.

Clone the repository:

```
git clone https://github.com/andrerochow/fsrt.git
cd fsrt
```

We recommend to create a new conda environment:

```
conda create -n fsrt python=3.9
conda activate fsrt
```

### Dependencies

This code requires at least Python 3.9 and PyTorch.

 1. Install [PyTorch](https://pytorch.org/get-started/locally/) (>= 1.12.0)

 2. Additional dependencies can be installed via:

    ```
    pip install -r requirements.txt
    ```
 3. In case you want to animate with relative motion transfer and automatically find a best-matching frame, you need to install the face-alignment library:

    ```
    git clone https://github.com/1adrianb/face-alignment
    cd face-alignment
    pip install -r requirements.txt
    python setup.py install
    ```

### Pretrained Checkpoints

Pretrained models can be found at [google-drive](https://drive.google.com/drive/folders/1R9BuWM-kqPddriZtIVf5z3Yq14D4DDSP?usp=drive_link).

The keypoint detector weights should be located at `fsrt_checkpoints/kp_detector.pt`. Note that all pretrained checkpoints are trained using the same keypoint detector weights.

## Animation Demo

#### Animate with Relative Motion Transfer (Better ID Preservation):

```
python demo.py --checkpoint fsrt_checkpoints/vox256.pt --config runs/vox256/vox256.yaml  --source_image path/to/source --driving_video path/to/driving  --source_idx 0 --relative --adapt_scale --find_best_frame
```

#### Animate with Absolute Motion Transfer:

```
python demo.py --checkpoint fsrt_checkpoints/vox256.pt --config runs/vox256/vox256.yaml  --source_image path/to/source --driving_video path/to/driving --source_idx 0
```

## Acknowledgement

Our FSRT implementation ist based on the PyTorch implementation of [Scene Representation Transformer](https://github.com/stelzner/srt) and [First Order Motion Model for Image Animation](https://github.com/AliaksandrSiarohin/first-order-model).

## BibTeX

```
@inproceedings{rochow2024fsrt,
  title={{FSRT}: Facial Scene Representation Transformer for Face Reenactment from Factorized Appearance, Head-pose, and Facial Expression Features},
  author={Rochow, Andre and Schwarz, Max and Behnke, Sven},
  booktitle={IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2024}
}
```
