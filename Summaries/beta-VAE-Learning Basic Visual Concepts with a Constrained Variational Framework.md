# beta-VAE: Learning Basic Visual Concepts with a Constrained Variational Framework

*Irina Higgins, Loic Matthey, Arka Pal, Christopher Burgess, Xavier Glorot, Matthew Botvinick, Shakir Mohamed, Alexander Lerchner*. **ICLR 2017**

## Summary

The paper augments the original VAE framework by modifying the variational ELBO by multiplying a factor beta (>1) to the latent loss term (KL divergence). This is done to encourage disentangled latent representations. The intuition provided in the paper for this is that by scaling up the latent loss term (which forces the latent distribution to match a unit Gaussian) in conjunction with the reconstruction loss will cause the model to learn the most efficient representation of the data, leading to disentanglement. However, by scaling up the latent loss term means the reconstruction loss is given less importance (compared to the original VAE), and as a result of this, beta-VAE reconstructions are of lower quality.

The paper also proposes quantitative method to measure the degree of disentanglement learned by different models. The method uses a linear classifier with low VC-dimensions to predict the disentangled factor.

## Strengths

- beta-VAE learns more and "cleaner" disentangled latent representations as compared to previous methods such as InfoGAN and DC-IGN.
- beta-VAE requires no design decisions or assumptions about the data and is stable to train.
- Achieves a high score on the proposed disentangled metric score.
- Everything is learned in a completely unsupervised manner.
- Extensive comparisons (qualitative and quantitative) with different methods are presented.

## Weaknesses / Notes

- The reasoning given in the paper for the cause of disentanglement due to scaling up the latent loss by beta is vague and not clear. Hard to develop intuition from the paper.
- Due to the VAE architecture used, generated images are blurry and the reconstructions are of low quality (even worse than normal VAEs).
- The many pages of mathematics in the paper ultimately results in just a multiplicative factor beta to the latent loss.
- No explanation is given (other than experimental) for the observation that using beta-VAE leads to to disentanglement whereas simply reducing the latent representation dimensions in normal VAEs doesn't. 