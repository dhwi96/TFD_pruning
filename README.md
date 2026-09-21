# Pruning-Guided Feature Distillation for an Efficient Transformer-Based Pose Estimation Model

This repository contains the research code for **Pruning-Guided Feature Distillation for an Efficient Transformer-Based Pose Estimation Model**.

The implementation is built on [MotionBERT](https://github.com/Walter0807/MotionBERT) and focuses on pruning experiments for transformer-based 3D human pose estimation. This is a research-code release rather than a mirror of the original MotionBERT repository.

## Repository scope

Included:

- pruning and sparsity experiment scripts;
- the minimal MotionBERT model, data-loader, loss, and utility modules required by those scripts;
- Human3.6M pose-estimation configuration files.

Not included:

- datasets;
- pretrained weights or experiment checkpoints;
- generated outputs and logs;
- unrelated MotionBERT tasks such as action recognition, mesh recovery, and in-the-wild inference;
- exploratory quantization code.

## Installation

```bash
conda create -n tfd-pruning python=3.7
conda activate tfd-pruning
# Install a PyTorch build compatible with your CUDA environment first.
pip install -r requirements.txt
```

## Data and checkpoints

Dataset files and model weights are intentionally excluded. Prepare the Human3.6M/MotionBERT data and a pretrained MotionBERT checkpoint locally, then update the paths passed to the scripts or stored in the YAML configuration files.

## Example

```bash
python BERT_global_pruning.py \
  --config configs/pose3d/MB_ft_h36m_pruning_test.yaml \
  --pruning 0.3 \
  --pretrained /path/to/pretrained/checkpoint \
  --checkpoint /path/to/output
```

Additional pruning variants and analysis utilities are provided in the root directory.

## Acknowledgement

This work uses MotionBERT as its transformer-based pose-estimation backbone. Please also cite the original MotionBERT work when using this code.

## Citation

Citation information for the paper will be added when it becomes available.
