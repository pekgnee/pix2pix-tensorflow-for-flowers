# pix2pix-tensorflow-for-flowers
Main Project for Advanced Computer Vision

The code for this project is taken (inspired) mostly from
https://affinelayer.com/pixsrv/
https://github.com/affinelayer/pix2pix-tensorflow
https://colab.research.google.com/github/anujdutt9/DeepLearning/blob/master/Colaboratory_Notebooks_for_pix2pix.ipynb

The initial intention was to run using data from 102 Category Flower Dataset
http://www.robots.ox.ac.uk/~vgg/data/flowers/102/index.html  
However it was taking too much time for Edge Detection on all 8189 images,  
and eventually the subset of 390 images (order selected by fate) comes from the incomplete run from  
https://github.com/pekgnee/Holistically-nested-edge-detection-for-flowers

Also it was observed that running the undocumented 'edges' operation from [pix2pix-tensorflow](https://github.com/affinelayer/pix2pix-tensorflow)  
gave slightly cleaner output than the initial 390 images.  
Hence edge detection was run again using the workflow mentioned under [creating-your-own-dataset](https://github.com/affinelayer/pix2pix-tensorflow#creating-your-own-dataset),  
but it requires set-up of environment for caffe, and this was copied from the colab notebook  
Edge detection with HED (holistically-nested edge detection)  
https://colab.research.google.com/drive/1SI57hLgHCX6mbZ2jNveNvq1Pqx07Jag7
