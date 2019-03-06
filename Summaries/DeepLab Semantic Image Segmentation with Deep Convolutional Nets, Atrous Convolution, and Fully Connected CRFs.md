# DeepLab: Semantic Image Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs

*Liang-Chieh Chen, George Papandreou, Iasonas Kokkinos, Kevin Murphy, Alan L. Yuille.* **IEEE Transactions on Pattern Analysis and Machine Intelligence 2018**

## Summary

Proposes the use of atrous convolutions (dilated convolutions) for addressing the task of semantic segmentation. The paper argues that the repeated downsampling caused due to the use of pooling layers can hamper dense prediction tasks where abstraction of spatial information is undesired. Instead of the pooling operation, atrous convolutions are used which is basically the same as normal convolution but using upsampled filters: enlarging the normal filter by introducing zeroes in between the filter values (hence, computation remains same). This has the effect of enlarging the field of view of the filter in the same way as pooling before applying filter would have done but with the added benefit of keeping the feature map size same and thus preserving spatial information.

However, computing feature responses at the original image resolution ends up being too costly. Hence, a hybrid approach is adopted which allows downsampling but by a smaller factor. Thus, the initial layers are simple conv layers and pooling layers but later layers are replaced with atrous convolutions.

## Strengths

- Re-purposes networks trained on image classification to the task of semantic segmentation.
- Proposes atrous spatial pyramid pooling encodes objects as well as image context at multiple scales.
- Advanced the state of the art on PASCAL VOC 2012 semantic image segmentation benchmark, PASCAL-Context, PASCAL-Person-Part and Cityscapes datasets.

## Weaknesses / Notes

- The use of CRF for post processing is just a roundabout method to improve the results the problem of which lies in poor architecture design (for example, convolutions in ASPP becomes 1x1 covolutions for values of atrous conv rate).
- The ASPP block has not been clearly explained in the paper and leads to confusion.