FROM tleyden5iwx/caffe-gpu-master

RUN apt-get update
RUN apt-get -y install python-pip
RUN apt-get -y install python-skimage
RUN apt-get -y install yasm
RUN pip install numpy matplotlib scipy

WORKDIR /home
RUN wget http://ffmpeg.org/releases/ffmpeg-3.0.1.tar.bz2
RUN tar -xvf ffmpeg-3.0.1.tar.bz2
WORKDIR /home/ffmpeg-3.0.1
RUN ./configure && make && make install

WORKDIR /home
RUN git clone https://github.com/ackimball/autocolorization
WORKDIR /home/autocolorization

RUN wget http://eecs.berkeley.edu/~rich.zhang/projects/2016_colorization/files/demo_v0/colorization_release_v0.caffemodel

RUN apt-get -y install libsnappy-dev
RUN apt-get -y install libgraphicsmagick-dev

RUN git clone https://github.com/torch/distro.git ~/torch --recursive
WORKDIR /home/torch 
RUN bash install-deps
RUN chmod 777 install.sh
RUN ./install.sh

WORKDIR /home
RUN luarocks install graphicsmagick # upgrade
RUN luarocks install lua-csnappy
RUN luarocks install md5
RUN luarocks install uuid

RUN git clone --depth 1 https://github.com/nagadomi/waifu2x.git
RUN mv waifu2x/* /home/autocolorization
