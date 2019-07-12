# Least Squares Generative Adversarial Networks

*Xudong Mao, Qing Li, Haoran Xie, Raymond Y.K. Lau, Zhen Wang, Stephen Paul Smolley*. **ICCV 2017**

## Summary

This paper proposes a change to the original GAN loss function which uses the sigmoid cross entropy by adopting the least squares loss function. Minimizing this objective results in minimizing the Pearson X<sup>2</sup> divergence. Unlike regular GANs, which cause no loss for samples that lie in a long way on the correct side of the decision boundary, LSGANs will penalize those samples as well. This moves the generated samples towards the decision boundary which results in them being closer to the manifold of real data. Also, penalizing such samples, leads to more gradients for updating the generator helping relieve the vanishing gradient problem.

## Strength

- LSGANs generates samples which are closer to the real data.
- Improved stability of the learning process.

## Weaknesses / Notes

- No quantitative method to measure the performances.