# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks

*Jun-Yan Zhu, Taesung Park, Phillip Isola, Alexei A. Efros.* **ICCV 2017**

## Summary

The paper proposes a method of unsupervised image-to-image translation using the Generative Adversarial Networks approach. The approach is based on two ideas: the images generated by the generator should be indistinguishable from the real images and second, the transformations should be cycle consistent. The first introduces the Adversarial Loss (similar to normal GANs) and the second leads to the Cycle Consistency Loss. Cycle consistency implies that on translating an image from one domain to the second and back to the original domain should result in the original image. Using the Cycle Consistency Loss also helps to constrain the number of possible translations which may exist for a given input image.

## Strengths

* Image-to-image translation without using labeled data.
* Generates good image translations for the desired domains.
* A single training procedure of the model allows both forward and backward translations.

## Weaknesses / Notes

- Gives poor results for image transfiguration.
- Doesn't generalize well to images with many instances.
- For the task of photo generation from paintings an additional identity loss term is introduced which regularizes the generator to be near an identity mapping when real samples of the target domain are provided as input.


