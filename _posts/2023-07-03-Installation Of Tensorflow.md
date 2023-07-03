---
layout: post
title: Installation of Tensorflow
author: mostafa
categories: [ Tensorflow, Toturials ]
tags: [ Tensorflow, Toturial, Python, Installation, Step By Step]
image: images/posts/tensorflow_python.jpg
description:
rating:

comments: true
featured: true
hidden: true
---

TensorFlow is a popular open-source framework for machine learning and deep learning. It provides a high-level API that allows you to easily build, train, and deploy models for various applications. In this blog post, I will show you how to install TensorFlow with pip, the standard package manager for Python, and other methods that you can use depending on your preferences and needs.

Installing TensorFlow with pip
------------------------------

The easiest way to install TensorFlow is to use pip, which is a command-line tool that lets you install and manage Python packages. To install TensorFlow with pip, you need to have Python 3.6 or higher installed on your system. You can check your Python version by running the following command in your terminal:

```
python --version
```

If you don't have Python installed, you can download it from the official website: https://www.python.org/downloads/

Once you have Python installed, you can install TensorFlow with pip by running the following command in your terminal:

```
pip install tensorflow
```

This will install the latest stable version of TensorFlow. If you want to install a specific version of TensorFlow, you can specify it after the package name, for example:

```
pip install tensorflow==2.6.0
```

This will install TensorFlow 2.6.0, which is the previous stable version.

You can also install TensorFlow with extra features or dependencies by adding brackets after the package name, for example:

```
pip install tensorflow[tfp]
```

This will install TensorFlow with TensorFlow Probability, which is a library for probabilistic modeling and inference.

To verify that TensorFlow is installed correctly, you can run the following Python code in your terminal or in a Jupyter notebook:

```python
import tensorflow as tf
print(tf.__version__)
```

This should print the TensorFlow version that you installed.

Installing TensorFlow with Anaconda
-----------------------------------

Another way to install TensorFlow is to use Anaconda, which is a distribution of Python that comes with many scientific and data analysis packages pre-installed. Anaconda also provides a graphical user interface called `Anaconda Navigator` that lets you manage your environments and packages.

To install TensorFlow with Anaconda, you need to have Anaconda installed on your system. You can download it from the official website: https://www.anaconda.com/products/individual

Once you have Anaconda installed, you can create a new environment for TensorFlow by running the following command in your terminal:

```
conda create -n tf_env python=3.8
```

This will create a new environment called tf_env with Python 3.8. You can choose any name and Python version that you like.

To activate the new environment, run the following command in your terminal:

```
conda activate tf_env
```

This will switch to the tf_env environment.

To install TensorFlow in the tf_env environment, run the following command in your terminal:

```
conda install tensorflow
```

This will install the latest stable version of TensorFlow from the Anaconda channel.

To verify that TensorFlow is installed correctly, you can run the same Python code as before:

```python
import tensorflow as tf
print(tf.__version__)
```

This should print the TensorFlow version that you installed.

To deactivate the tf_env environment, run the following command in your terminal:

```
conda deactivate
```

This will switch back to the base environment.

Installing TensorFlow from Source
---------------------------------

The third way to install TensorFlow is to build it from source code. This method gives you more control over the configuration and optimization of TensorFlow, but it also requires more time and technical skills. You may want to use this method if you want to use the latest development version of TensorFlow, or if you want to customize TensorFlow for your specific hardware or platform.

To install TensorFlow from source, you need to have some prerequisites installed on your system, such as `Git`, `Bazel`, `Python`, `pip`, and `NumPy`. You can find the detailed instructions for each operating system on the official website: https://www.tensorflow.org/install/source

Once you have the prerequisites installed, you can clone the TensorFlow repository from GitHub by running the following command in your terminal:

```
git clone https://github.com/tensorflow/tensorflow.git
```

This will download the source code of TensorFlow to your local directory.

To build TensorFlow from source, you need to configure it according to your preferences and needs. You can do this by running the following command in your terminal:

```
./configure
```

This will prompt you to answer some questions about the options and features that you want to enable or disable for TensorFlow.

After configuring TensorFlow, you can build it by running the following command in your terminal:

```
bazel build //tensorflow/tools/pip_package:build_pip_package
```

This will compile the source code and generate a pip package for TensorFlow.

To install the pip package that you built, run the following command in your terminal:

```
pip install /tmp/tensorflow_pkg/tensorflow-*.whl
```

This will install the TensorFlow pip package that you built.

To verify that TensorFlow is installed correctly, you can run the same Python code as before:

```python
import tensorflow as tf
print(tf.__version__)
```

This should print the TensorFlow version that you built.

---

I prefered `pip` to do the installation, but you can choose the method that suits your preferences and needs. I hope you found this post helpful and informative. Next, on next posts I'm going to give you an example of how to do a hello world on with this. 