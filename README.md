# pix2pix-tensorflow-for-flowers

### Source Code
The code for pix2pix_tensorflow_for_flowers.ipynb is taken (inspired) mostly from:  
* https://affinelayer.com/pixsrv/
* https://github.com/affinelayer/pix2pix-tensorflow

### Training Data
The initial intention was to train using the 102 Category Flower Dataset
http://www.robots.ox.ac.uk/~vgg/data/flowers/102/index.html  
Due to time constraint, eventually only 390 of the 8189 images were used for training.

### Preprocessing
Edge detection was run using the workflow mentioned under [creating-your-own-dataset](https://github.com/affinelayer/pix2pix-tensorflow#creating-your-own-dataset), with the undocumented 'edges' operation.
This requires set-up of environment for caffe, and this was copied from the colab notebook  
Edge detection with HED (holistically-nested edge detection)  
https://colab.research.google.com/drive/1SI57hLgHCX6mbZ2jNveNvq1Pqx07Jag7

### Folders
| Folder | Description |
|--------|-------------|
| flower_training | images in a side-by-side combined image that pix2pix.py expects |
| flowers_training_output | output of training |
| flowers_test_output | test results |

See also [Summary of results](https://pekgnee.github.io/pix2pix-tensorflow-for-flowers/flowers_test_output/)

### Post implementation
[Series of colab for pix2pix](https://colab.research.google.com/github/anujdutt9/DeepLearning/blob/master/Colaboratory_Notebooks_for_pix2pix.ipynb) was found.  
It does not seem to originate from the original pix2pix authors, and may differ slightly in the implementation.

### On hindsight
