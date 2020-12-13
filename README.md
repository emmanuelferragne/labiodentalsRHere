# Labiodentals /r/ here to stay
<p align="center">
<img src="https://github.com/emmanuelferragne/labiodentalsRHere/blob/main/imOccAndEllipse.png" width="800"/>
</p>

This repo contains links to the deep learning models we used in our forthcoming publication.

If you are only interested in visualizing the neural network architecture we used for **classification**, download the model [here](https://cloud.parisdescartes.fr/index.php/s/wWzdgGzm47pks7J) in ONNX format, and open it with the freely available [Neutron visualizer](https://github.com/lutzroeder/netron).

If you are only interested in visualizing the neural network architecture we used for **semantic segmentation**, download the model [here](https://cloud.parisdescartes.fr/index.php/s/AJJyJZLWPiSci3T) in ONNX formant, and open it with the freely available [Neutron visualizer](https://github.com/lutzroeder/netron).

If you have Matlab Deep Learning Toolbox and want to replicate our **classification**, dowload the model [here](https://cloud.parisdescartes.fr/index.php/s/qemjePfsrj7649t) and the two .bmp images from this repo. Then, in Matlab:
```Matlab
load netAllRvsW.mat
% visualize network
analyzeNetwork(netAllRvsW)
%load demo image
imName = 'demoRClassif.bmp';
%alternatively:
%imName = 'demoWClassif.bmp';
% crop image to extract upper part (front cam) and resize
myIm = imresize(imcrop(imread(imName), [2, 8, 765, 290]), [300, 800]);
% view image
imshow(myIm)
% classify image
hatLabel = classify(netAllRvsW, myIm);

```
If you have Matlab Deep Learning Toolbox and Computer Vision Toolbox and want to see how our **semantic segmentation** model works, download the model [here](https://cloud.parisdescartes.fr/index.php/s/XBSKkAsdXGX4rsG) and the demo .png image from this repo. Then, in Matlab:
```matlab
load segnetMouth.mat
% visualize network
analyzeNetwork(segnetMouth)
%load demo image
myIm = imread('RForSegmentation.png');
%label pixels
mySeg = semanticseg(myIm, segnetMouth);
%define colormap
cmap = [255 0 0; 0 0 255]/255;
%overlay segmentation
outImClass = labeloverlay(myIm, mySeg, 'Colormap', cmap);
%plot image
imshow(outImClass);


```
Alternatively, you can (theoretically) open the ONNX files containing both network architecture and weights with your favourite deep learning framework. 
# Cite
coming soon...

# Contact
If you have questions about this research, please feel free to send an email to [Hannah King](mailto:hannahhmking@gmail.com) or [Emmanuel Ferragne](mailto:emmanuel.ferragne@u-paris.fr)
