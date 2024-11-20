# CycleGAN Monet Style Transfer

## Project Overview
This project explores the use of CycleGANs to transform photos into Monet-style paintings. The task involves building and training a generative model that learns bidirectional mappings between two domains: photos and Monet paintings. The generated images are evaluated based on their artistic quality and adherence to Monet's style.

## Dataset
- **Monet Paintings:** 300 images of Monet-style paintings in `.tfrec` format.
- **Photos:** Over 7000 landscape photos in `.tfrec` format.
- Images are resized to `128x128` and normalized to the range `[-1, 1]` for training efficiency.

## Model Architecture
- **Generators:** U-Net-inspired architectures with skip connections to transform images between domains.
- **Discriminators:** PatchGAN models that evaluate image authenticity on a patch level.
- **Loss Functions:**
  - **Adversarial Loss:** Encourages realistic image generation.
  - **Cycle Consistency Loss:** Preserves content during domain translation.
  - **Identity Loss:** Ensures unchanged output for images already in the target domain.

## Training
- **Mixed Precision:** Enabled for faster training on GPUs.
- **Optimizers:** Adam with an exponential decay schedule.
- **Epochs:** 25 epochs, with 300 steps per epoch.
- **Batch Size:** 4 images per batch.

## Results
- The model generates decent Monet-style paintings with clear stylistic transformations, despite using reduced image dimensions for faster training.
- Sample visualizations demonstrate effective translation of photos into Monet-like artwork.

## Submission Packaging
- 300 generated images are saved as `.jpg` files and archived into a `submission.zip` file for Kaggle submission.

## Future Improvements
- Train with larger image dimensions for finer details.
- Experiment with additional data augmentation techniques to improve robustness.
- Optimize hyperparameters for better style fidelity and artistic quality.

## References
This implementation was strongly inspired by [Amy Jang's CycleGAN tutorial](https://www.kaggle.com/code/amyjang/monet-cyclegan-tutorial).

