autocolorization
==================
We used pretrained convolutional neural networks (CNNs) to automatically colorize, denoise, and upscale a portion of Godard's Breathless (1960).

We accomplished this by leveraging pretrained models released by the authors of two recent papers:    
[1] Gustav Larsson, Michael Maire, and Gregory Shakhnarovich. "Learning Representations for Automatic Colorization," In arXiv, Mar 2016. http://arxiv.org/pdf/1603.06668v1.pdf    
[2] Chao Dong, Chen Change Loy, Kaiming He, Xiaoou Tang, "Image Super-Resolution Using Deep Convolutional Networks", In arXiv, Jan 2015. http://arxiv.org/abs/1501.00092

We created a docker container so users can easily colorize, denoise, and upscale their own videos on any machine that has docker installed (although you'll need a good GPU to do this quickly).


<a href="https://www.youtube.com/watch?v=Mlss8RF-v7I
" target="_blank"><img src="http://i.imgur.com/fK5Mn7M.png" 
alt="autocolorization" width="848" height="478" border="10" /></a>



Examples & Usage
================
Colorizing your video: 
----------------------
1) Break video into individual frames and extract audio
```
./movie2frames.sh your_video.avi 
```

2) Run colorization on frames
```
python autocolorization.py
```

3) Recreate video using the colorized frames
```
./frames2movie.sh new_frames
```

Colorizing and upscaling your video:
------------------------------------
1) Break video into individual frames and extract audio
```
./movie2frames your_video.mp4 frames png
```

2) Run colorization on frames
```
python autocolorization.py
```

3) Denoise and upscale the frames   
```
find ./frames -name "*.png" |sort > frames.txt
mkdir new_frames
[lua call]
```

4) Recreate video with colorized and upscaled frames
```
avconv -f image2 -r 24 -i new_frames/%d.png -i audio.mp3 -r 24 -vcodec libx264 -crf 16 video.mp4
```


Installation & Setup
====================
We provide a separate dockerfiles for CPUs and GPUs. The docker containers are provisioned for colorization and upscaling.

Docker
------
```
docker run -it ackimball/autocolorization-gpu /bin/bash
```
or    
```
docker run -it ackimball/autocolorization-cpu /bin/bash
```

Dependencies
------------
- Caffe
- Torch
- ffmpeg
- avconv
- waifu2x
