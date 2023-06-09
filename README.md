# **HellenicDrones**
**Drones Machine Vision Augmentation.**

# **Tutorial for on device Computer Vision inference using yolov8.**

📌 Hey, Everything is still under development. 🔨

## Installation
Use [miniconda](https://docs.conda.io/en/latest/miniconda.html) 🐍 a free minimal installer for conda 
(The place in which we will create the environment in which the programs will run).

Download the installer [here](https://docs.conda.io/en/latest/miniconda.html#windows-installers) 
for Windows. 🪟

![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/fcb49ec5-15a4-4d03-8647-0b50eeb794e8)


We will download Python ``version 3.10`` which comes with Conda 23.3.1 Python 3.10.10 
released on April 24, 2023. 🐍

After the installation is completed we will search and open Anaconda Prompt which is an "enhanced"
windows cmd which automatically includes the conda installation of Python to your PATH environment variable meaning
there is no need to set the PYTHONPATH environment variable.

After everything is installed you should see something like this.


![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/2b7302ca-5316-4097-b7f1-a8d178e03f62)


💡 If you run into any issues or need more guidance visit [here](https://conda.io/projects/conda/en/stable/user-guide/install/index.html#installation).

⚡ To speed up the process of installing new depedencies we will use Libmamba a faster conda solver
which can yield +(50-80)% resolving speeds.
Do this by running the following commands on Anaconda Prompt:
```bash
conda update -n base conda
```
and
```bash
conda install -n base conda-libmamba-solver
conda config --set solver libmamba
```
💡For more info [here](https://www.anaconda.com/blog/a-faster-conda-for-a-growing-community).

## Setting up the environment

We need to install the necesary dependencies which are required, to do this we should be **Creating** 
a new environment by using the following command:
```bash
conda create --name yolov8 python=3.10
```
We named the new env yolov8 and used python version 3.10.
Afterwards we need to **activate** the new env by
```bash
activate yolov8
```
The (base) on the parathesis should now be changed to your new env name for me yolov8.

![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/82b70a3e-ef3e-463a-a9da-129dfbf5db11)

📘 We can skip all of the above if we are gonna just use this project and follow the below steps instead on the
(base) env. 📢 It is not recomended as package issues might occures if future changes or prototyping happens.

💡 Here is a fast getting started [tutorial](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html)
and a helpful conda [cheatsheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf).

## Installation of the Project

Now let's start with the fun part start by running on the activated conda environment in my case (yolov8):
```bash
pip install ultralytics
```
This gonna a take a while as it is downloading all the necessary packages and their depedencies 
to train, evaluate, predict and export a yolov8 model. 🔥

📢 This downloads the CPU 💻 version of Pytorch if you have a GPU ⚡ to run the model on you need to go to
[Pytorch](https://pytorch.org/get-started/locally/)

and install it with the apropriate cuda version by coping the command.

![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/60b1d1c0-10d7-4e15-95db-f988d062aabc)

and running it on Anaconda Prompt by putting a ``--upgrade`` in front of torch like this:

```bash
pip3 install --upgrade torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
```

To check if everything has gone smoothly type ``python`` followed by an ``import torch`` followed by a ``torch.__version__``  and ``torch.cuda_is_available()`` ( if you have a gpu) finally to exit type ``exit()``.

![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/37f10c0f-d8e9-4caf-86c0-96b43f2608c6)

## Downloading the pretrained model.
Click [this](https://github.com/nikogarro/HellenicDrones/raw/main/best.pt) or

Go to https://github.com/nikogarro/HellenicDrones and click on best.pt (this is the default pytorch model) and then download the raw file.

![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/81d99eaf-ad57-4595-aece-da7f636466d2)

That's it everything is Set up! 📐

## Usage

On Anaconda Prompt use the following commands while being on the right env (yolov8) for inference. 🔥
```bash
yolo task=detect mode=predict model=path_to_the_downloaded_model show=True source=your_image_or_video_directory line_width=1
```

💡 For webcam use ``source=0`` and alternative for any other image or video formats including streaming ``RTSP, RTMP, HTTP`` and all the acceptable arguments see detailed guide [here](https://docs.ultralytics.com/modes/predict/)

📢To stop the real time camera prediction press and hold **``q``**.


![εικόνα](https://github.com/nikogarro/HellenicDrones/assets/117863158/ec5eb756-0c1e-4e05-82f4-bc07f6dc0b80)







