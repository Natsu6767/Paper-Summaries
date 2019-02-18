# InfoVAE: Information Maximizing Variational Autoencoders

*Shengjia Zhao, Jiaming Song, Stefano Ermon.* **arXiv, 2017**

## Summary

The paper proposes methods to solve the problem that variational autoencoders tend to ignore the latent code, storing all the required information for reconstructions in the decoder parameters itself. This undermines the purpose of unsupervised representation learning, as the latent representation contain little to know information. According to the paper, the problem is caused due to the regularization term in the ELBO (KL divergence) and removing this will solve the problem. However, by only using the reconstruction loss for the error function makes it impossible to do ancestral sampling (which is an important feature of VAEs). The only way to sample now is by using a Markov chain.

The paper proposes multiple methods to solve the information maximization between latent representations and reconstructions based on changing the divergence (from KL) used for the regularization in the ELBO:

- Adversarial Training
- Stein Variational Gradient
- Maximum-Mean Discrepancy (MMD)

Out of the above, MMD-VAE gives the best results.

## Strengths

- MMD-VAE helps maximize the mutual information between the latent representations and the reconstructions while still allowing ancestral sampling.
- Extensive experiments have been performed and presented.
- Log likelihood estimate comparison between different proposed methods and the original ELBO is given.

## Weaknesses / Notes 

- MMD is a framework to quantify the distance between two distributions by comparing all of their moments. It can be efficiently implemented using the kernel trick.

- No clear explanation and intuition is provided for normal VAEs not creating informative latent representations.