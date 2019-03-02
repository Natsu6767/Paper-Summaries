# Learning Disentangled Joint Continuous and Discrete Representations

*Emilien Dupont.* **NIPS 2018**

## Summary

The paper proposes a method to adapt the Beta-VAE loss function, which only uses continuous latent representations, to use both discrete and continuous latent code. This results in the disentanglement of the data generating factors using the most appropriate distribution, eg. digit type is encoded using discrete and latent code and rotation (tilt) using a continuous latent code. The continuous latent code is parameterized by a factorized Gaussian with the prior being a unit Gaussian. The discrete latent code is parametrized using Gumbel Softmax Distributions while the prior is a uniform Gumbel Softmax Distribution.

## Strengths

-  The capacities of the discrete and continuous latent channels are controlled separately forcing the model to encode information both in the discrete and continuous channels.
- Use of the VAE framework results in stable training (unlike InfoGAN).
- Completely unsupervised.
- The learned encoder can be used as a good inference network. It gives 88.7% accuracy on MNIST classification even though no supervision was given while training.
- Extensive experiments on a number of datasets are done and presented in the paper along with hyperparameters used.

## Weaknesses / Notes

- The whole paper proposes the use of discrete latent code and how to disentangle them. Everything else is the same as Beta-VAE.
- Due to increasing the weight of the latent loss terms in the loss function to cause disentanglement, the reconstructions are of lower quality.