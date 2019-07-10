# InstaGAN: Instance-aware Image-to-Image Translation

*Sangwoo Mo, Minsu Cho, Jinwoo Shin.* **ICLR 2019**

## Summary

The paper proposes a method for unpaired cross-domain image-to-image translation that translates both an image and the corresponding set of instance segmentation masks. Doing this helps tackle the cases where the image has multiple instances and involves significant changes in shape. The method involves encoding both the input image and the instance segmentation masks followed by combining these encodings in appropriate ways (by concatenation) to generate the image in the desired domain along with the corresponding instance segmentation masks in the new domain. The discriminator is given both the image and the segmentation masks as input to output real image or generated image.

The loss consists of two terms: the domain loss, which makes the generated outputs to follow the style of a target domain, and the content loss, which makes the outputs to keep the original contents. The GAN loss is used for the domain loss. The content loss consists of the cycle-consistency loss, the identity mapping loss and the new proposed context preserving loss. The context preserving loss enforces to translate the instances only while keeping the background same.

## Strengths

- Image transfiguration gives good results.
- Handles cases which have multiple instances really well.
- The training procedure used, sequential mini-batch translation, allows the network to be trained in limited GPU memory which otherwise would be difficult in cases where there are many instances.
- The given training method also gives better translation results due to its data augmentation effect.

## Weaknesses / Notes

- The paper provides results on a limited number of domains (3 pairs). It is difficult to say how well the method will work with other categories.
- Complex training.