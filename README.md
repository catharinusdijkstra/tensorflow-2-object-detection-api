# README #

## Introduction

Welcome to my **tensorflow-2-object-detection-api** repository. In this repository, you
find the **object_detection** package with code useful for object detection. The code
stored in the object_detection package is a direct copy of the
[TensorFlow 2 Object detection API](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/) that can be used for object detection in images and videos.

The codebase in this repository can be directly imported in your own Python code for
object detection, or it can be used to setup a Python environment
**tf2-object_detection** from which all functionalities in this repository can be run
locally and unit tests can be performed.

## Why use this repository for object detection?

First, the TensorFlow 2 Object detection API is part of the [TensorFlow Model Garden](https://github.com/tensorflow/models). The TensorFlow Model Garden is a repository with a number of
different models and modeling solutions for TensorFlow users. The typical first step
when using the TensorFlow Model Garden involves cloning the entire repository. In the
case of object detection, cloning the entire repository results in installing more
functionalities than are strictly needed for object detection. This repository solves
this by only installing those functionalities needed for object detection. Using the
copy in this repository thus provides all the required functionalities, without
functionalities that are not needed for object detection. The resulting code is easy to
install and can be directly used for object detection in your own Python code.

Second, installing the code that is required for object detection with TensorFlow from
scratch can be challenging. In this repository I've attempted to remove these challenges
by providing a code base that can be easily installed and used directly.

## Requirements

1. An Integrated Development Environment (IDE) such as for example
[Visual Studio Code](https://code.visualstudio.com/).
2. [conda](https://docs.conda.io/projects/conda/en/stable/).
3. [Protocol Buffer Compiler](https://protobuf.dev/).

The codebase in this repository can be directly imported in your own Python code for
object detection, or it can be used to setup a Python environment tf2-object-detection
from which all functionalities in this repository can be run locally and unit tests can
be performed.

### How was this repository created?

For reproducibility of this repository, the code below is shown in order to illustrate
how it was originally created.

I first installed the Protocol Buffer Compiler. Since I work with Ubuntu on WSL
(<https://ubuntu.com/wsl>), I used the following command:

```
sudo apt install protobuf-compiler
```

Protocol Buffer Compiler installation instructions for other setups can be found
[here](https://grpc.io/docs/protoc-installation/).

Next, I ran the following commands from the root folder of this repository:

```
git clone https://github.com/tensorflow/models.git
cp -PRf models/research/object_detection object_detection
rm -Rf models
cp object_detection/packages/tf2/setup.py .
protoc object_detection/protos/*.proto --python_out=.
```

## Installation of this repository

To use this repostory in your own Python code you first need to install it using
[pip](https://pypi.org/project/pip/). This can be done from the command line into two
ways.

The first way is simply by running the following command:

```
pip install https://github.com/catharinusdijkstra/tensorflow-2-object-detection-api
```

The second way is to create a new **requirements.txt** file and include the line

```
git+https://github.com/catharinusdijkstra/tensorflow-2-object-detection-api
```

, or if you already have a requirements.txt file with any other packages you want to
install, simply add this line to this already existing file. Then run the following
command:

```
pip install -r requirements.txt
```

## Setup the Python environment tf2-object-detection locally (optional)

In order to setup the Python environment tf2-object-detection locally, run the following
commands from the root folder of this repository:

```
conda env update --file environment.yml
conda activate tf2-object-detection
```

This will create and activate the Python environment tf2-object-detection from which all
functionalities in this repository can be run locally and unit tests can be performed.

Note that this step is optional. This step is not needed for direct use of the
object_detection package in your own Python code. All that is required for that are the
installation instructions from the previous step.

## How to use this repository in your own code

After installation, open a Python program and/or Jupyter notebook and import the package
cdtools and/or its sub-packages and modules using the Python commands **import** and
**from**. For example:

```
import object_detection
from object_detection import *
```

You can now use the functionalities within the object_detection package for object
detection.
