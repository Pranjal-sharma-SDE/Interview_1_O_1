# Computer Vision Interview Questions

This folder contains interview questions focused on Computer Vision concepts, algorithms, and deep learning architectures.

## Topics Covered

1. **Image Processing Fundamentals**
2. **Object Detection**
3. **Image Segmentation**
4. **CNN Architectures**
5. **Advanced Topics**

---

## Questions

### 1. What are convolutional operations and why are they effective for images?
**Answer:** Convolution applies a learnable filter (kernel) across an image by computing element-wise multiplication and summation. Benefits:
- **Parameter sharing**: Same weights used across spatial locations
- **Local connectivity**: Captures local patterns (edges, textures)
- **Translation invariance**: Detects features regardless of position
Key parameters: kernel size, stride, padding, number of filters.

### 2. Explain the difference between object detection and image segmentation.
**Answer:** 
- **Object Detection**: Locates objects with bounding boxes and classifies them. Output: boxes + class labels.
- **Semantic Segmentation**: Classifies each pixel into a class category. No instance distinction.
- **Instance Segmentation**: Identifies each object instance at pixel level. Combines detection + segmentation.
Examples: YOLO/Faster R-CNN for detection; U-Net/DeepLab for segmentation.

### 3. What is the architecture of YOLO (You Only Look Once)?
**Answer:** YOLO is a single-shot object detector:
- Divides image into S×S grid
- Each cell predicts B bounding boxes and confidence scores
- Simultaneously predicts class probabilities
- Single forward pass for detection (real-time capable)
Advantages: Fast inference, global context understanding. Versions: YOLOv1 through YOLOv8 with progressive improvements.

### 4. Explain data augmentation for computer vision.
**Answer:** Data augmentation artificially expands training data:
- **Geometric**: Rotation, flipping, scaling, cropping, translation
- **Color**: Brightness, contrast, saturation adjustments
- **Advanced**: Mixup, CutMix, Random Erasing, AutoAugment
Benefits: Reduces overfitting, improves generalization, especially with limited data.

### 5. What is the difference between R-CNN, Fast R-CNN, and Faster R-CNN?
**Answer:** Evolution of region-based detectors:
- **R-CNN**: Selective search for regions → CNN features → SVM classification. Slow (2000 regions per image).
- **Fast R-CNN**: Single CNN pass for entire image → RoI pooling → classification + regression. Much faster.
- **Faster R-CNN**: Region Proposal Network (RPN) replaces selective search. End-to-end trainable, near real-time.

### 6. What is feature pyramid network (FPN)?
**Answer:** FPN addresses multi-scale object detection by building a pyramid of features:
- **Bottom-up pathway**: Standard CNN forward pass
- **Top-down pathway**: Upsamples high-level features
- **Lateral connections**: Combines low-level (detailed) and high-level (semantic) features
Result: Strong features at all scales, improves detection of objects of various sizes.

### 7. Explain the U-Net architecture for segmentation.
**Answer:** U-Net is an encoder-decoder architecture:
- **Encoder (contracting path)**: Convolutions + max pooling, captures context
- **Decoder (expanding path)**: Up-convolutions + concatenation with encoder features
- **Skip connections**: Preserve fine-grained details from encoder
Designed for biomedical image segmentation, works well with limited training data.

### 8. What is non-maximum suppression (NMS)?
**Answer:** NMS removes overlapping bounding box predictions:
1. Sort boxes by confidence score
2. Keep highest confidence box
3. Remove all boxes with IoU > threshold with kept box
4. Repeat until no boxes remain
Variants: Soft-NMS (reduces scores instead of removing), DIoU-NMS (considers distance).

### 9. Explain Intersection over Union (IoU) and its applications.
**Answer:** IoU measures overlap between predicted and ground truth boxes:
- IoU = Area of Intersection / Area of Union
- Range: 0 (no overlap) to 1 (perfect match)
Applications:
- Evaluation metric (mAP uses IoU thresholds)
- NMS threshold for removing duplicates
- Loss function component (IoU loss, GIoU, DIoU, CIoU)

### 10. What are Vision Transformers (ViT) and how do they differ from CNNs?
**Answer:** ViT applies transformer architecture to images:
- Splits image into fixed-size patches (e.g., 16×16)
- Linearly embeds each patch + positional encoding
- Processes through standard transformer encoder
- Classification token for final prediction
Differences from CNNs: No inductive bias for locality, requires more data for training but achieves better results at scale. Variants: DeiT, Swin Transformer, BEiT.
