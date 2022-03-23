# Face-detection-in-RPI
This repository is a detailed guide on how to make a face detection API run on your raspberry pi with complete steps

The readme file contains:
- Which Packages to download
- Which compononents to buy
- How to run code

## Buying components
Here is a list of all the components used
- Raspberry pi 4b+ 4gb ram
- Raspberry PI 5MP Camera Board Module
- Monitor
- Keyboard
- Mouse

## Setting up opencv
Once you have put the raspbian buster image into to rpi we need to install opencv. To do so just give the commands:
```bash
pip install picamera[array]
Sudo apt-get update
Sudo apt-get upgrade
sudo apt install cmake build-essential pkg-config git
sudo apt install libjpeg-dev libtiff-dev libjasper-dev libpng-dev libwebp-dev libopenexr-dev
sudo apt install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev libdc1394-22-dev libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev
sudo apt install libgtk-3-dev libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt install libatlas-base-dev liblapacke-dev gfortran
sudo apt install libhdf5-dev libhdf5-103
sudo apt install python3-dev python3-pip python3-numpy

sudo nano /etc/dphys-swapfile
sudo systemctl restart dphys-swapfile
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
mkdir ~/opencv/build
cd ~/opencv/build

cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules \
-D ENABLE_NEON=ON \
-D ENABLE_VFPV3=ON \
-D BUILD_TESTS=OFF \
-D INSTALL_PYTHON_EXAMPLES=OFF \
-D OPENCV_ENABLE_NONFREE=ON \
-D CMAKE_SHARED_LINKER_FLAGS=-latomic \
-D BUILD_EXAMPLES=OFF ..
make -j$(nproc)

sudo make install
sudo ldconfig
pip install face-recognition --no-cache-dir

pip install imutils

sudo nano /etc/dphys-swapfile
sudo systemctl restart dphys-swapfile

git clone
```
