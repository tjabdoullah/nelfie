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
