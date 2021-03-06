PsyCam
============

![Alt text](sample_dream.jpg?raw=true "DeepDream")

Google DeepDream
-----------------------------
The Google DeepDream algorithm is a modified neural network. Instead of
identifying objects in an input image, it changes the image into the direction
of its training data set, which produces impressive surrealistic, dream-like images.
You can find the original GitHub repository at
https://github.com/google/deepdream/blob/master/dream.ipynb

PsyCam
-------------------------
PsyCam is an extension of the DeepDream for the Raspberry Pi. With the RPi
camera module, PsyCam can take a photo and convert it into a DeepDream.

Installation
------------------
Either follow the manual installation instructions at

    http://www.knight-of-pi.org/deepdream-on-the-raspberry-pi-3-with-raspbian-jessie/

or perform the following steps for the semi-automated installation:

    $ mkdir ~/deepdream && cd ~/deepdream
    $ git clone https://github.com/JoBergs/PsyCam
    $ cd PsyCam
    $ python install_tools.py packages
    $ python install_tools.py caffe
    $ python install_tools.py protobuf
    $ python install_tools.py camera
    $ sudo reboot

The installation will take half a day or so. The installer script should also work
on most modern Ubuntu systems.

Usage
-----------------------------------
The script psycam.py is controlled via command-line parameters. They are listed with

    $python psycam.py --help

Start PsyCam with randomized layer and octave. This requires an attached and enabled 
Raspberry Pi camera module.

    $python psycam.py

Start PsyCam with an input image instead of a camera snapshot (required for non-RPi usage!):

    $python psycam.py -i sky_small.jpg

Make snapshots with the given size width height (large sizes will crash the RPi):

    $python psycam.py -s 400 300

Make snapshots and convert them to dreams continually:

    $python psycam.py -c

Start PsyCam set layer depth, type and octave manually:

    $python psycam.py -d 2 -t 1 -o 6

Create a new network model file:

    $python psycam.py -n

Output images
--------------------------------

The dreams are stored in

    ~/deepdream/PsyCam/dreams 

with the original photo and tagged with a timestamp.


Have fun
---------------

Author:
[Johannes Bergs](mailto:jo@knight-of-pi.org)
