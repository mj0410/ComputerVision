# Image Classification of real dogs and AI generated dogs

### Data Collection

- Real dog images from [Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/)
- Fake dog images from Google Image `Image_Crawling.py` with keyword `AI generated dog`, `AI generated puppy`, `AI generated real dog`, `generated dog image`, and `realistic AI generated dog`
- Remove images with other dogs, with people, with watermark, or with text

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
- Residual connection (skip connection)

<img src="https://github.com/mj0410/cv_classification/assets/66175878/f359e83c-d80d-4372-9e1a-b26b10e80314">
