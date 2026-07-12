# GAN Training Stability on an 8-Mode Gaussian Mixture

This project investigates the training behavior of Saturating Vanilla GAN,
Non-Saturating GAN, and Wasserstein GAN on a synthetic two-dimensional,
eight-mode Gaussian mixture dataset.

The objective was to study mode coverage, mode collapse, discriminator
behavior, sensitivity to random initialization, and differences between
standard GAN and Wasserstein objectives.

## Models

- Saturating Vanilla GAN
- Non-Saturating GAN
- Wasserstein GAN with weight clipping

The generator maps two-dimensional Gaussian noise to two-dimensional samples.
The Vanilla GAN discriminator produces a real/fake probability, while the WGAN
critic produces an unrestricted real-valued score.

## Dataset

The dataset contains 50,000 two-dimensional samples drawn from eight Gaussian
components positioned uniformly around a unit circle.

- Number of modes: 8
- Radius: 1.0
- Variance per Gaussian: 0.0025
- Standard deviation: 0.05



## Evaluation

The models were evaluated using:

- Mode coverage
- Generated-sample scatter plots
- Discriminator heatmaps
- KDE density estimates
- Generator and discriminator/critic loss curves
- Repeated experiments across multiple random seeds
- Vanilla GAN and WGAN comparison

## Results

In these experiments:

- Both the final Vanilla GAN and WGAN recovered all 8 modes.
- The Vanilla GAN generated tighter clusters around the Gaussian centers.
- The WGAN generated samples more broadly across the ring.
- Repeated-seed experiments were used to evaluate whether results were
  consistent across different model initializations.
- Recovering all modes did not necessarily mean that two models learned the
  same sample distribution.


