# Image-to-Image Translation with Conditional Adversarial Networks

*Phillip Isola, Jun-Yan Zhu, Tinghui Zhou, Alexei A. Efros*. **CVPR 2017**

## Summary

This paper provides a solution to the image-to-image translation problem using conditional adversarial networks. The network consists of two parts: the generator and the discriminator. The generator used is based on the U-Net architecture involving skip connections. This allows easy transfer of low-level information from the input to the output. The paper introduces a new type of discriminator architecture called the PatchGAN. The job of this discriminator is to classify if each N x N patch in an image is real or fake.

## Strengths

- Generates sharp and clear images.
- Removes the need to manually find an appropriate loss function for each translation task since GANs are able to learn the appropriate function.
- Many experiments have been done and presented in the paper related to architecture modifications and ablation of the loss function.

## Weaknesses / Notes

- Requires paired labeled data which is hard to get.
- To the objective function, along with the normal GAN objective, a L1 distance loss between synthesized image and the ground-truth image is added.
- Dropout is also applied at test time to introduce noise and stochasticity.
- Batch normalization during test time is applied using the statistics of the test batch and not the aggregated statistics of the training batch.

