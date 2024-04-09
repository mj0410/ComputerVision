# Image Classification of real dogs and AI generated dogs

## Data Collection

- Real dog images from [Stanford Dogs Dataset](http://vision.stanford.edu/aditya86/ImageNetDogs/)
- Fake dog images from Google Image `Image_Crawling.py` with keyword `AI generated dog`, `AI generated puppy`, `AI generated real dog`, `generated dog image`, and `realistic AI generated dog`
- Remove images with other dogs, with people, with watermark, or with text

## GoogLeNet

### Image Classification Result

<img src="https://github.com/mj0410/cv_classification/assets/66175878/c1123b84-a372-43d5-9bdc-b4d1f0b43be0" width="700"> </br>
</br>

### Model Evaluation

<img src="https://github.com/mj0410/cv_classification/assets/66175878/24d4798a-9ef5-4235-a7a9-a45677cb1a44" width="300">
<img src="https://github.com/mj0410/cv_classification/assets/66175878/e7944d78-eeb1-4320-a8a9-0f96b2f60ebb" width="300"> </br>
</br>

### Model Introduction

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

## ResNet

### Image Classification Result

<img src="https://github.com/mj0410/cv_classification/assets/66175878/5c0560de-a2a0-42e6-a19a-c2c100d80cd4" width="700"> </br>
</br>

### Model Evaluation

<img src="https://github.com/mj0410/cv_classification/assets/66175878/83d141c6-1a45-4aa7-afd0-fe10df2fcf82" width="300">
<img src="https://github.com/mj0410/cv_classification/assets/66175878/c8ad23de-278a-465c-820f-4bcfcac986ec" width="300"> </br>
</br>

### Model Introduction

[Deep Residual Learning for Image Recognition](https://arxiv.org/pdf/1512.03385.pdf)

- introduced to overcome gradient vanishing or exploding in deep neural network
- Residual connection (skip connection)

<img src="https://github.com/mj0410/cv_classification/assets/66175878/f359e83c-d80d-4372-9e1a-b26b10e80314">
