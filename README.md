# Dense Transformer Networks

This is the tensorflow implementation of our recent work, "Dense Transformer Networks". Please check the [paper](https://arxiv.org/abs/1705.08881) for details.

## Introduction

In this work, we propose Dense Transformer Networks to apply spatial transformation to semantic prediction tasks. 
Dense Transformer Networks can extract features based on irregular areas, whose shapes and sizes are based on data.
In the meanwhile, Dense Transformer Networks provide a method that efficiently restore spatial information.

```
@article{li2017dtn,
  title={Dense Transformer Networks},
  author={Jun Li and Yongjun Chen and Lei Cai and Ian Davidson and Shuiwang
Ji},
  journal={arXiv preprint arXiv:1705.08881},
  year={2017}
}
```


## Experimental results:
1. CelebA dataset

![image](https://github.com/divelab/Spatial-VAE-via-MVND/blob/master/results/celeba_new.png)

2. Cifar dataset

![image](https://github.com/divelab/Spatial-VAE-via-MVND/blob/master/results/cifar_new.png)


In both figures above, the first and second rows shows training images and images generated by the original VAEs. The
remaining three rows are the results of naïve spatial VAEs, spatial VAEs via MVN distributions and
spatial VAEs via low-rank MVN distributions, respectively.

For details of our work, please refer to [Spatial Variational Auto-Encoding via Matrix-Variate Normal Distributions](https://arxiv.org/abs/1705.06821).



## Datasets:

Our experiments are based on [cifar 10](https://www.cs.toronto.edu/~kriz/cifar.html) and [cropped celebA datasets](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html). We provide data reader for those two datasets. For celebA dataset, please convert it to h5 file first then call the data reader.

You can use other datasets such as [The Street View House Numbers (SVHN) Dataset](http://ufldl.stanford.edu/housenumbers/) or [LSUN Dataset](http://lsun.cs.princeton.edu/2016/) as well. Just write a simple data reader file. 

## How to run it

1. Clone or download this repository to your working directory.
2. Get the datasets ready.
3. Set related arguments in main.py. There are two models: vanilla VAE and our Spatial VAE. Set "model_name" as 'vanilla' to call tranditional VAE and set as 'low_rank' to call our Spatial VAE.
4. Call ``` python main.py ``` or  ``` python main.py --action=train ``` to train the model.
5. If you wish to use "parzen window" to evaluate the model, set a checkpoint in arguments for the model to reload and then call ``` python main.py --action=test```.






