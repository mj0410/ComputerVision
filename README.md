# Computer Vision

### Models

```diff
# Image Segmentation
FCN, U-Net, U-Net+++, SAM

# Classification
GoogleNet, VGG, ResNet, EfficientNet

# Detection
RCN, Fast RCN, Faster RCNN, YOLO, SSD, RetinaNet, EfficientDet

# 3D
VoxelNet (`V` means volume)
```

------

### VGGNet

<img src ="https://github.com/mj0410/NVIDIA_AI_Academy/assets/66175878/a7abf881-4ab8-4e5b-8a0b-d4a725c8df35">

### GoogLeNet

[Going deeper with convolutions](https://arxiv.org/pdf/1409.4842.pdf)

- Go deeper to improve performance
    - prob 1) overfitting
    - prob 2) use of computational resources too high,,
    - solution ➔ sparsely connect! </br>
        <img src ="https://github.com/mj0410/NVIDIA_AI_Academy/assets/66175878/02cf9c7d-1ca4-4de8-9168-9a7afa4f9d41" width="300">

- bottleneck layer

    ```mermaid
    graph BT;
        layer_b[Previous Layer];
        layer_t[Filter concatenation];
        filter1[1X1 Conv Layer];
        filter2[3X3 Conv Layer];
        filter3[5X5 Conv Layer];
        layer_b --> filter1;
        layer_b --> filter2;
        layer_b --> filter3;
        filter1 --> layer_t;
        filter2 --> layer_t;
        filter3 --> layer_t;
    ```
    - v1) 3 layers of 1X1, 3X3, 5X5 ➔ v2) 4 layers of 1X1, 3X3, 2 connected 3X3s (result size of 2 3X3s is same as 5X5)

### ResNet

[Deep Residual Learning for Image Recognition](https://arxiv.org/pdf/1512.03385.pdf)

- introduced to overcome gradient vanishing or exploding in deep neural network
- 152 layers
- Residual connection (skip connection)

### EfficientNet

### EfficientDet

[EfficientDet: Scalable and Efficient Object Detection](https://arxiv.org/pdf/1911.09070.pdf)

### Transformer

- encoder + decoder structure
- give information where to focus on (attention score)
- positional encoding (info of order)
- `Attention is All You Need`

##### Vision Transformer (ViT)

[AN IMAGE IS WORTH 16X16 WORDS: TRANSFORMERS FOR IMAGE RECOGNITION AT SCALE](https://arxiv.org/pdf/2010.11929.pdf)

- Transformer instead of CNN structure
- Divide image as patches, tokenize each patch
- Swin Transformer
