# Stylenet

This is a quick implementation of http://arxiv.org/abs/1508.06576

## Requirements
chainer
http://chainer.org

## Quick Usage
```
pip install chainer
wget http://www.robots.ox.ac.uk/%7Evgg/software/very_deep/caffe/VGG_ILSVRC_19_layers.caffemodel
python style_net.py -g 3 -c kinkaku.jpg -s style.png -d kinkaku
```

## Comment
There is a hard coding part. The computation of L_style in forward()
This part is coresponding to equation (4) and (5).
I did not paramatalized it because it would be too complizated. 
I think defalt is fine, but if you want, you can easily change it directly. See L_style in forward().

I recommend to make content image a squired size.
However, you can use rectangular one, but the output will be forsed to a squire.
You need to resize agian, ex in python,
```
from scipy.misc import imread, imresize
img = imread('filename.png')
img = imresize(img,[400,300])
```

Basic settings is configured, in #Settings part, which is just after the import sentences.
20000 iteraton will be done. Image is saved every 500 iteration.