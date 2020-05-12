# nelfie
A couple python lines of code to take daily pictures of my child with a little toy.

# setup
Follow this link to setup open CV: https://www.pyimagesearch.com/2019/09/16/install-opencv-4-on-raspberry-pi-4-and-raspbian-buster/

# install these commands
sudo apt-get purge wolfram-engine
sudo apt-get purge libreoffice*
sudo apt-get clean
sudo apt-get autoremove
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install build-essential cmake pkg-config
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libfontconfig1-dev libcairo2-dev
sudo apt-get install libgdk-pixbuf2.0-dev libpango1.0-dev
sudo apt-get install libgtk2.0-dev libgtk-3-dev
sudo apt-get install libatlas-base-dev gfortran
sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
sudo apt-get install python3-dev

# virtual envirement

wget https://bootstrap.pypa.io/get-pip.py
sudo python get-pip.py
sudo python3 get-pip.py
sudo rm -rf ~/.cache/pip
sudo pip install virtualenv virtualenvwrapper
nano ~/.bashrc
source ~/.bashrc
mkvirtualenv open_cv_venv -p python3

## then edit ~/.bashrc and add these at the end

export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
source /usr/local/bin/virtualenvwrapper.sh
export VIRTUALENVWRAPPER_ENV_BIN_DIR=bin

## then
source ~/.bashrc
mkvirtualenv cv -p python3


# install Pi Camera
pip install "picamera[array]"

# install open cv
pip install opencv-contrib-python==4.1.0.25


# issues, of course
We CV2 won't be inported easily and it will cause a bug, if you check the comments on the tutorial, you will find in the comments section someone referring to a link providing a solution, here is the link: https://blog.piwheels.org/how-to-work-out-the-missing-dependencies-for-a-python-package/
Apparently some libraries need to get updated, I followed this link that provied a solution.
Here is the list of commands I followed to properly import cv2:

cd /home/pi/.local/lib/python3.7/site-packages/cv2
ls -l
ls
ldd cv2.cpython-35m-arm-linux-gnueabihf.so
ldd cv2.cpython-37m-arm-linux-gnueabihf.so 
ldd cv2.cpython-37m-arm-linux-gnueabihf.so | grep "not found"
sudo apt install apt-file
sudo apt-file update
apt-file search libjasper.so.1
sudo apt install libjasper1

