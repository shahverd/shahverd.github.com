---
layout: post
title: Use TensorFlow with Docker
author: mostafa
categories: [ TensorFlow, Tutorials]
tags: [ TensorFlow, Docker, Installation, Programming]
image: images/posts/docker-tensorflow.png
description: A quick tutorial about how to use tensorflow with docker on Linux. 
rating:

comments: true
featured: false
hidden: false
---

How to Use TensorFlow with Docker
---------------------------------
TensorFlow is a popular open-source framework for machine learning and data analysis. It allows you to build, train and deploy neural networks and other models for various tasks, such as image classification, natural language processing, computer vision and more.

Docker is a tool that creates virtual environments that isolate a TensorFlow installation from the rest of the system using containers. Containers are lightweight and portable units that contain all the dependencies and configurations needed to run a specific application. TensorFlow programs run in a container that can share resources with the host machine, such as directories, GPU, internet, etc.

Using TensorFlow with Docker has many benefits, such as:

- ***Easy installation and setup***: You don't need to install TensorFlow or any other libraries on your host machine. You just need to install Docker and pull the TensorFlow image from the Docker Hub repository.
- ***Reproducibility and portability***: You can run the same TensorFlow container on any machine that has Docker installed, without worrying about compatibility issues or environment differences.
- ***GPU support***: Docker is the easiest way to enable TensorFlow GPU support on Linux, since only the NVIDIA® GPU driver is required on the host machine. The NVIDIA® CUDA® Toolkit does not need to be installed.

In this blog post, we will learn how to use TensorFlow with Docker on Linux. We will cover the following topics:

- How to install Docker and NVIDIA Docker support
- How to download a TensorFlow Docker image
- How to start a TensorFlow Docker container
- How to run TensorFlow programs in a container
- How to use Jupyter notebooks in a container

How to install Docker and NVIDIA Docker support
----------------------------------------------
Before we can use TensorFlow with Docker, we need to install Docker and NVIDIA Docker support on our host machine. Here are the steps:

- Install Docker on your local host machine by following the instructions here: <https://docs.docker.com/engine/install/>
- To run the docker command without sudo, create the docker group and add your user by following the post-installation steps here: <https://docs.docker.com/engine/install/linux-postinstall/>
- Install NVIDIA Docker support to enable GPU support by following the instructions here: <https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html>
- Take note of your Docker version with `docker -v`. Versions earlier than 19.03 require `nvidia-docker2` and the `--runtime=nvidia` flag. On versions including and after 19.03, you will use the `nvidia-container-toolkit` package and the `--gpus all` flag.

How to download a TensorFlow Docker image
-----------------------------------------
The official TensorFlow Docker images are located in the `tensorflow/tensorflow` Docker Hub repository. You can find them here: <https://hub.docker.com/r/tensorflow/tensorflow/>

Image releases are tagged using the following format:

{:class="table table-bordered"}
| Tag     |  Description |
| ------- | ------------ |
| latest  | The latest release of TensorFlow CPU binary image. Default. |
| nightly | Nightly builds of the TensorFlow image. (Unstable.) |
| version | Specify the version of the TensorFlow binary image, for example: 2.8.3 |

Each base tag has variants that add or change functionality:

{:class="table table-bordered"}
| Tag Variants | Description |
| ------------ | ----------- |
| tag-gpu | The specified tag release with GPU support. |
| tag-jupyter | The specified tag release with Jupyter (includes TensorFlow tutorial notebooks) |

You can use multiple variants at once. For example, the following downloads TensorFlow release images to your machine:

```
docker pull tensorflow/tensorflow # latest stable release
docker pull tensorflow/tensorflow:devel-gpu # nightly dev release w/ GPU support
docker pull tensorflow/tensorflow:latest-gpu-jupyter # latest release w/ GPU support and Jupyter
```

How to start a TensorFlow Docker container
------------------------------------------
To start a TensorFlow-configured container, use the following command form:
```
docker run [-it] [--rm] [-p hostPort:containerPort] tensorflow/tensorflow[:tag] [command]
```
For details, see the docker run reference: <https://docs.docker.com/engine/reference/run/>. Here are some examples of how to start a TensorFlow Docker container:

- To start an interactive bash shell in a CPU-only container:
```
docker run -it --rm tensorflow/tensorflow bash
```
- To start an interactive bash shell in a GPU-enabled container (requires NVIDIA Docker support):
```
docker run -it --rm --gpus all tensorflow/tensorflow:latest-gpu bash
```
- To start a Jupyter notebook server in a CPU-only container and access it from your browser at http://localhost:8888:
```
docker run -it --rm -p 8888:8888 tensorflow/tensorflow:latest-jupyter
```
- To start a Jupyter notebook server in a GPU-enabled container and access it from your browser at http://localhost:8888 (requires NVIDIA Docker support):
```
docker run -it --rm --gpus all -p 8888:8888 tensorflow/tensorflow:latest-gpu-jupyter
```

How to run TensorFlow programs in a container
--------------------------------------------
Once you have started a TensorFlow Docker container, you can run TensorFlow programs in it using the Python interpreter or the Jupyter notebook server. Here are some examples of how to run TensorFlow programs in a container:

- To verify the TensorFlow installation using the Python interpreter in a CPU-only container:
```
docker run -it --rm tensorflow/tensorflow \
python -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
```
- To verify the TensorFlow installation using the Python interpreter in a GPU-enabled container (requires NVIDIA Docker support):
```
docker run -it --rm --gpus all tensorflow/tensorflow:latest-gpu \
python -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
```
- To verify the TensorFlow installation using the Jupyter notebook server in a CPU-only container and access it from your browser at http://localhost:8888:
```
docker run -it --rm -p 8888:8888 tensorflow/tensorflow:latest-jupyter
```
- To verify the TensorFlow installation using the Jupyter notebook server in a GPU-enabled container and access it from your browser at http://localhost:8888 (requires NVIDIA Docker support):
```
docker run -it --rm --gpus all -p 8888:8888 tensorflow/tensorflow:latest-gpu-jupyter
```

Conclusion
------------
We learned:

- How to use TensorFlow with Docker on Linux
- How to install Docker and NVIDIA Docker support 
- How to download a TensorFlow Docker image
- How to start a TensorFlow Docker container
- How to run TensorFlow programs in a container 

We also learned about the benefits of using TensorFlow with Docker, such as easy installation and setup, reproducibility and portability, and GPU support.

We hope you enjoyed this blog post and learned something new. If you have any questions or feedback, feel free to leave a comment below.