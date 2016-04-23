autocolorization
==================
We used pretrained convolutional neural networks (CNNs) to automatically colorize, denoise, and upscale a portion of Godard's Breathless (1960).

We accomplished this by leveraging pretrained models released by the authors of two recent papers:    
[1] Gustav Larsson, Michael Maire, and Gregory Shakhnarovich. "Learning Representations for Automatic Colorization," In arXiv, Mar 2016. http://arxiv.org/pdf/1603.06668v1.pdf    
[2] Chao Dong, Chen Change Loy, Kaiming He, Xiaoou Tang, "Image Super-Resolution Using Deep Convolutional Networks", In arXiv, Jan 2015. http://arxiv.org/abs/1501.00092

We created a docker container so users can easily colorize, denoise, and upscale their own videos on any machine that has docker installed (although you'll need a good GPU to do this quickly).

Start the docker container
==========================
```
docker run -it ackimball/autocolorization /bin/bash
```


Examples & Usage
================
1. Break video into individual frames

2. Run colorization on frames

3. Denoise and upscale the frames   

4. Recreate video with colorized frames



Installation & Setup
====================
Coming soon



