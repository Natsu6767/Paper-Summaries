# High-Resolution Image Synthesis and Semantic Manipulation with Conditional GANs

*Ting-Chun Wang, Ming-Yu Liu, Jun-Yan Zhu, Andrew Tao, Jan Kautz, Bryan Catanzaro*. **CVPR 2018**

## Summary

This work improves provides high resolution image synthesis from semantic segmentation maps by using a coarse-to-coarse generator, a multi-scale discriminator architecture, and an improved adversarial learning objective function. Along with the semantic segmentations maps the method also utilizes instance information in the form of boundary map. This helps in the generation of sharper images. The generator is decomposed into two sub-networks, the global generator network and the local enhancer network. The global generator takes 1024 x 512 resolution as input whereas the local enhancer takes an input of resolution 2048 x 1024. Three discriminators are used which have identical network structure but operate at different image scales. Along with the original resolution, images downsampled by a factor of 2 and 4 are passed to the discriminators. The original GAN loss is compounded with the feature matching loss which involves extracting features from multiple layers of the discriminator and match these intermediate representations between the real and generated image.

## Strengths

- Generates high resolution sharp images.
- Provides a way to utilize the GANs framework for high resolution image generation which was thought to be unstable.
- Allows easy manipulation of semantic data to get desired output photo-realistic image.

## Weaknesses / Notes

- Somewhat complex training procedure involving first training the global generator and then the local enhancer.
- Requires labeled data, hence, making it difficult to extend to other domains.
- An additional perceptual loss (VGG feature loss) is added to the loss function which helps improve the results.