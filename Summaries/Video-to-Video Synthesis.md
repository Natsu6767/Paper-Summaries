# Video-to-Video Synthesis

*Ting-Chun Wang, Ming-Yu Liu, Jun-Yan Zhu, Guilin Liu, Andrew Tao, Jan Kautz, Bryan Catanzaro.* **NeurIPS 2018**

## Summary

The paper provides a method for supervised video-to-video translation by using the conditional adversarial networks framework. To obtain the output conditional distribution a sequential generator is used based on a Markov assumption: the generation of the *t*-th frame depends on three factors, current source frame, past *L* source frames, and past *L* generated frames. To model this, a feed-forward network is used which consists of two parts: the first corresponds to pixels warped from the previous frame using estimated optical flow, and the second part hallucinates new pixels.
Two discriminators are used. Conditional image discriminator ensures that each output frame resembles a real image given the same source image. Conditional video discriminator ensures that consecutive output frames resemble the temporal dynamics of a real video given the same optical flow. The final loss function of the whole network consists of the adversarial (GAN) loss using the two discriminators and the optical flow loss (consists of two terms: the first is the endpoint error between the ground truth and the estimated flow, and the second is the warping loss when the flow warps the previous frame to the next frame).

## Strengths

- Good intuitive explanation is provided for the proposed method (generation of each frame).
- 2048 x 1024 resolution outputs with minimal flickering as compared to previous methods.
- Provides high-level control over the video generation results. For example, you can easily replace all the buildings with trees in the segmentation map to generate the desired video with trees in the background.

## Weaknesses / Notes

- The method requires labeled data which is difficult to acquire.
- VGG feature matching loss and discriminator feature matching loss are added to the learning objective to improve the training stability.
- The generator uses a coarse-to-fine architecture. 