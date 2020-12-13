# labiodentalsRHere

This repo contains links to the deep learning models we used in our forthcoming publication.

If you are only interested in visualizing the neural network architecture we used for **classification**, download the model [here](https://cloud.parisdescartes.fr/index.php/s/wWzdgGzm47pks7J) in ONNX format, and open it with the freely available [Neutron visualizer](https://github.com/lutzroeder/netron).

If you are only interested in visualizing the neural network architecture we used for **semantic segmentation**, download the model [here](https://cloud.parisdescartes.fr/index.php/s/AJJyJZLWPiSci3T) in ONNX formant, and open it with the freely available [Neutron visualizer](https://github.com/lutzroeder/netron).

If you have Matlab Deep Learning Toolbox and want to replicate our **classification**, dowload the model [here](https://cloud.parisdescartes.fr/index.php/s/qemjePfsrj7649t) and the two .bmp images from this repo. Then in Matlab:
```matlab
load netAllRvsW.mat
% visualize network
analyzeNetwork(netAllRvsW)
%load demo image
imName = 'demoRClassif.bmp';
%alternatively:
%imName = 'demoWClassif.bmp';
% crop and resize
myIm = imresize(imcrop(imread(imName), [2, 8, 765, 290]), [300, 800]);
% view image
imshow(myIm)
% classify image
hatLabel = classify(netAllRvsW, myIm);

```

