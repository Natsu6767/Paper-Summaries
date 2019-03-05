# Disentangling by Factorising

*Hyunjik Kim, Andriy Mnih.* **ICML 2018**

## Summary

The paper aims to solve to problem caused by methods such as Beta-VAE for disentanglement which sacrifice the reconstruction quality for better disentanglement. The paper splits the latent loss term of the original VAE and shows that it is composed of two terms: **I(x; z) + KL(q(z)||p(z))**. Penalizing the KL term encourages independence in the dimensions and thus disentangling by pushing q(z) towards the factorial prior p(z). On the other hand, penalizing I(x; z) reduces the amount of information about x stored in z, which leads to poor reconstructions for high values of Beta. 

The paper augments the VAE objective by introducing a Total Correlation term weighed by Gamma. This term is optimized using the density-ratio trick by using an MLP similar to the GAN objective.

## Strengths

- Better reconstructions for the same amount of disentanglement as compared to Beta-VAE.
- The optimization of TC is done by minimizing the divergence between two distributions over the latent space which are low dimensional and have overlapping support (for GANs the distributions are high dimensional and have disjoint support).
- A new disentanglement metric is proposed which uses a majority-vote classifier and the error rate of the classifier giving metric score. It is also free of hyperparameters and simple.
- Extensive experiments have been done and results clearly presented.

## Weaknesses / Notes

- The proposed metric is unsuitable for data with non-independent factors of variations.
- Discrete latent variables cannot be used, thus the model fails to capture discrete factors of variations.
- Low TC is necessary but not sufficient for meaningful disentangling.