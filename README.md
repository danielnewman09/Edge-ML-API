# Edge-ML-API

This repository contains the code to run inference on the edge. This code has been tested on the Raspberry Pi 3 B+.

[Taken from Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-uswgi-and-nginx-on-ubuntu-18-04#step-4-%E2%80%94-configuring-uwsgi)

## Create Python Environment

First, download the necessary packages

```bash
sudo apt update
sudo apt install python3-pip python3-dev build-essential libssl-dev libffi-dev python3-setuptools
```
Install the package necessary to build virtual environments.

```bash
sudo apt install python3-venv
```

Clone this repository and begin working in it

```bash
cd ~/
git clone https://github.com/danielnewman09/Edge-ML-API.git
cd Edge-ML-API
```

Create a virtual environment and begin working in it

```bash
python3.7 -m venv apienv
source apienv/bin/activate
```
While working in the virtual environment, install the necessary Python packages to run the REST API

```bash
pip install wheel uwsgi flask
```

Install the packages necessary to run Tensorflow

[Taken from Stack Exchange](https://raspberrypi.stackexchange.com/questions/107483/error-installing-tensorflow-cannot-find-libhdfs-so)

```bash
sudo apt-get install -y libhdf5-dev libc-ares-dev libeigen3-dev
python3 -m pip install keras_applications==1.0.8 --no-deps
python3 -m pip install keras_preprocessing==1.1.0 --no-deps
python3 -m pip install h5py==2.9.0
sudo apt-get install -y openmpi-bin libopenmpi-dev
sudo apt-get install -y libatlas-base-dev
python3 -m pip install -U six wheel mock
```

Install the packages necessary to run Tensorflow Lite

```bash
pip install https://dl.google.com/coral/python/tflite_runtime-2.1.0.post1-cp37-cp37m-linux_armv7l.whl
```

Install other packages

```bash
pip install scipy
```






