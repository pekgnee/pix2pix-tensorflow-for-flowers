# pix2pix-tensorflow-for-flowers

### Source Code
The code for pix2pix_tensorflow_for_flowers.ipynb is taken (inspired) mostly from:  
* https://affinelayer.com/pixsrv/
* https://github.com/affinelayer/pix2pix-tensorflow

### Training Data
The initial intention was to train using the [102 Category Flower Dataset](http://www.robots.ox.ac.uk/~vgg/data/flowers/102/index.html)  
Due to time constraint, eventually only [390](https://github.com/pekgnee/pix2pix-tensorflow-for-flowers/blob/master/390flowers.zip) of the 8189 images were used for training.  
Refer to folder [flowers_training](https://github.com/pekgnee/pix2pix-tensorflow-for-flowers/tree/master/flowers_training)

### Preprocessing
Edge detection was run using the workflow mentioned under [creating-your-own-dataset](https://github.com/affinelayer/pix2pix-tensorflow#creating-your-own-dataset), with the undocumented 'edges' operation. This requires special environment set-up for caffe, and this was copied from another colab notebook [Edge detection with HED (holistically-nested edge detection)](https://colab.research.google.com/drive/1SI57hLgHCX6mbZ2jNveNvq1Pqx07Jag7)

As the built-in 'edges' operation resizes the image to 256x256, the original colour image also needs to undergo the 'resize' operation, before applying the 'combine' operation to create training images in a side-by-side combined image that pix2pix.py expects

### Training
Took 5 hours in Colab with GPU Runtime

### Folders
| Folder | Description |
|--------|-------------|
| flower_training | images in a side-by-side combined image that pix2pix.py expects |
| flowers_training_output | output of training |
| flowers_test_output | test results |

### Test Results
[10 test images](https://github.com/pekgnee/pix2pix-tensorflow-for-flowers/blob/master/flowers_test.zip) were randomly selected from [ImageNet - flower](http://image-net.org/explore?wnid=n11669921) and the same preprocessing above was applied.  
The test results are summarized in [flowers_test_output/index.html](https://pekgnee.github.io/pix2pix-tensorflow-for-flowers/flowers_test_output/).

**Observations:**  
With 390 training images, pix2pix was able to fill in the outline with common flower colours,  
including a very rough feature at the centre of flower.  
The background are mostly green with very little detail, and probably quite hard to be generalized / learnt from the training image set.

### Possible improvements
- Training image data set  
  Subject shld be easily isolated from background, eg. like the shoe & handbag images from the original paper (possibly coming from a product catalog) and few distracting details in the background
- Preprocessing  
  Use some existing segmentation / detector to detect for the main subject, before applying Edge Detection within the bounding box, to avoid having edges from details in the background
- Increase training data  
  Only 390 of the 8189 images had been used in this case
- Periodic saving of checkpoints to external location  
  In order to continue training in case of Colab automatic disconnection

### Post implementation
[Series of colab for pix2pix](https://colab.research.google.com/github/anujdutt9/DeepLearning/blob/master/Colaboratory_Notebooks_for_pix2pix.ipynb) was found, but it does not seem to originate from the original pix2pix authors, and may differ slightly in the implementation.


