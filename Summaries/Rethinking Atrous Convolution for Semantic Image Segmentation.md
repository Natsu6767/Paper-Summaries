# Rethinking Atrous Convolution for Semantic Image Segmentation

*Liang-Chieh Chen, George Papandreou, Florian Schroff, Hartwig Adam.* **arXiv 2017**

## Summary

Improves upon the original DeepLab paper on semantic segmentation by removing the DenseCRF layer. The paper also provides better design decisions for the atrous convolutions. The paper experiments with two approaches. The first is to use the atrous convolutions with different rates in cascade and thus making the network deeper. While the second approach splits the network into multiple parallel paths after a certain point with each parallel path having a different rate for the atrous convolutions, creating a pyramid structure (Atrous Spatial Pyramid Pooling).

The paper also proposes a solution with the earlier implementation of ASPP in which for large rates for atrous convolutions, instead of capturing the whole image context, the filter degenerates to a simple 1x1 filter. The solution is to apply global average pooling on the last feature map (before splitting into parallel paths) to encode the global context information.

## Strengths

- Improves over the previous DeepLab versions.
- Comparable performance with other state-of-the-art models on PASCAL VOC 2012 semantic image segmentation benchmark.
- Removed the use of CRFs.

## Weaknesses / Notes

- Multi-grid method has been used for setting the rates for the atrous convolutions in each block in the network.