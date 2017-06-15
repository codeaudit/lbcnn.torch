# LBCNN
Torch implementation of CVPR'17 - Local Binary Convolutional Neural Networks http://xujuefei.com/lbcnn.html


(this repo is under construction)


### Abstract
We propose **local binary convolution (LBC)**, an efficient alternative to convolutional layers in standard convolutional neural networks (CNN). The design principles of LBC are motivated by local binary patterns (LBP). The LBC layer comprises of a set of fixed sparse pre-defined binary convolutional filters that are not updated during the training process, a non-linear activation function and a set of learnable linear weights. The linear weights combine the activated filter responses to approximate the corresponding activated filter responses of a standard convolutional layer. The LBC layer affords significant parameter savings, 9x to 169x in the number of learnable parameters compared to a standard convolutional layer. Furthermore, the sparse and binary nature of the weights also results in up to 9x to 169x savings in model size compared to a standard convolutional layer. We demonstrate both theoretically and experimentally that our local binary convolution layer is a good approximation of a standard convolutional layer. Empirically, CNNs with LBC layers, called **local binary convolutional neural networks (LBCNN)**, achieves performance parity with regular CNNs on a range of visual datasets (MNIST, SVHN, CIFAR-10, and ImageNet) while enjoying significant computational savings.

***

### Overview
<img src="http://xujuefei.com/lbcnn_image/01_LBP_3_5.png" width="300"><img src="http://xujuefei.com/lbcnn_image/02_LBP.png" width="520">

We draw inspiration from local binary patterns that have been very successfully used for facial analysis.

<img src="http://xujuefei.com/lbcnn_image/03_LBCNN_CNN.png" width="820">

Our LBCNN module is designed to approximate a fully learnable dense CNN module.

<img src="http://xujuefei.com/lbcnn_image/04_sparsity_2.png" width="260"><img src="http://xujuefei.com/lbcnn_image/04_sparsity_4.png" width="260"><img src="http://xujuefei.com/lbcnn_image/04_sparsity_9.png" width="260">


Binary convolutional kernels with different sparsity levels.

<img src="http://xujuefei.com/lbcnn_image/05_theory.png" width="820">

***

### Contributions

* Convolutional kernels inspired by local binary patterns.
* Convolutional neural network architecture with **non-mutable randomized sparse binary convolutional kernels**.
* Lightweight CNN with massive computational and memory savings.

***

### References

* Felix Juefei-Xu, Vishnu Naresh Boddeti, and Marios Savvides, [**Local Binary Convolutional Neural Networks**](felix_cvpr17_lbcnn.pdf),
* To appear in *IEEE Computer Vision and Pattern Recognition (CVPR), 2017*. (Spotlight Oral Presentation)


```
@inproceedings{juefei-xu2017lbcnn,
 title={{Local Binary Convolutional Neural Networks}},
 author={Felix Juefei-Xu and Vishnu Naresh Boddeti and Marios Savvides},
 booktitle={IEEE Computer Vision and Pattern Recognition (CVPR)},
 month={July},
 year={2017}
}
```


***

### Implementations

```javascript
function test() {
 console.log("look ma’, no spaces");
}
```

* MNIST

```bash
th main.lua -netType resnet-binary-felix -dataset mnist -data '/media/Freya/juefeix/LBCNN' -save '/media/Freya/juefeix/LBCNN-Weights' -numChannels 16 -batchSize 10 -depth 75 -full 128 -sparsity 0.5
```

* SVHN

```bash
th main.lua -netType resnet-binary-felix -dataset svhn -data '/media/Freya/juefeix/LBCNN' -save '/media/Freya/juefeix/LBCNN-Weights' -numChannels 16 -batchSize 10 -depth 40 -full 512 -sparsity 0.9
```
* CIFAR-10


