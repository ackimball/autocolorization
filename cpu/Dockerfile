FROM tleyden5iwx/caffe-cpu-master

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





