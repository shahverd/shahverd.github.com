---
layout: post
title: Hello World in TensorFlow
author: mostafa
categories: [ TensorFlow, Toturials ]
tags: [ TensorFlow, Hello World, Programming, AI, Machine Learning]
image: images/posts/hello-world.jpg
description: Learn how to write a simple `Hello World` program in TensorFlow, which is the first program you should learn to develop in TensorFlow.
rating:

comments: true
featured: false
hidden: false
---

Hello World in TensorFlow
-------------------------

TensorFlow is a popular open-source framework for machine learning and data analysis. It allows you to build, train and deploy neural networks and other models for various tasks, such as image classification, natural language processing, computer vision and more.

In this blog post, we will learn how to write a simple `Hello World` program in TensorFlow, which is the first program you should learn to develop in TensorFlow. We will use TensorFlow 2, which is the latest version of TensorFlow that has many improvements and new features compared to TensorFlow 1.

What is the "Hello World" program in TensorFlow?
------------------------------------------------

The "Hello World" program in TensorFlow is a simple program that outputs "Hello, world!" to the console. It does not use any machine learning or data analysis, but it shows how to import TensorFlow, create a constant tensor and print its value.

A tensor is a generalization of vectors and matrices to higher dimensions. It is the basic data structure in TensorFlow, and it can store numbers, strings or other types of data. A constant tensor is a tensor whose value does not change.

Here is the code for the "Hello World" program in TensorFlow:

```python
# Import TensorFlow
import tensorflow as tf

# Create a constant tensor
hello = tf.constant("Hello, world!")

# Print the tensor
print(hello)
```

If you run this code, you should see something like this:

```python
tf.Tensor(b'Hello, world!', shape=(), dtype=string)
```

The output shows that the tensor has a shape of (), which means it is a scalar (a single value), and a dtype of string, which means it stores a string value. The b prefix indicates that the string is encoded as bytes.

How to run the "Hello World" program in TensorFlow?
--------------------------------------------------

There are different ways to run the "Hello World" program in TensorFlow, depending on your development environment and preferences. Here are some of the common options:

- **Google Colab**: Google Colab is a free online platform that allows you to write and execute Python code in your browser. It has TensorFlow and other libraries pre-installed, and it provides access to GPUs and TPUs for faster computation. You can use Google Colab to run the "Hello World" program by following these steps:

    1. Open this link: <https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/quickstart/beginner.ipynb>
    2. This will open a notebook that contains the code for the "Hello World" program and other examples.
    3. Click on the "play" button on the left side of the code cell that contains the "Hello World" program.
    4. Wait for the code to run and see the output below the cell.

- **Local IDE**: If you have Python installed on your local machine, you can use any IDE (Integrated Development Environment) of your choice to run the "Hello World" program. Some popular IDEs are PyCharm, Visual Studio Code, Spyder, etc. You will also need to install TensorFlow 2 on your local machine by following these instructions: [Installation Of Tensorflow](Installation-Of-Tensorflow.html). To run the "Hello World" program on your local IDE, follow these steps:

    1. Create a new Python file and name it hello_world.py.
    2. Copy and paste the code for the "Hello World" program into the file.
    3. Save the file and run it from your IDE or from the command line by typing python hello_world.py.
    4. See the output on your console or terminal.

- **GPU on Local Mahine or Cloud Service**: If you have a GPU (Graphics Processing Unit) on your local machine or on a cloud service, you can use it to speed up the computation of TensorFlow programs. To use a GPU, you will need to install some additional libraries and drivers, such as `CUDA` and `cuDNN`. You can find more details on how to set up TensorFlow with GPU support here: <https://www.tensorflow.org/install/gpu>. To run the "Hello World" program on a GPU, follow these steps:

    1. Make sure you have installed TensorFlow 2 with GPU support on your machine or cloud service.
    2. Add the following line at the beginning of your `hello_world.py` file: `tf.config.set_visible_devices([], 'GPU')`. This will tell TensorFlow to use only GPUs for computation.
    3. Run your hello_world.py file as before and see if there is any difference in speed or output.

Conclusion
----------
We learned how to write and run a simple "Hello World" program in TensorFlow 2. This program does **not** use any machine learning or data analysis, but it shows how to import TensorFlow, create a constant tensor and print its value. We also learned how to run the program on different platforms, such as Google Colab, local IDE and GPU.

This is just the beginning of your TensorFlow journey. There are many more things you can do with TensorFlow, such as: 

 - building and training neural networks
 - loading and processing datasets
 - visualizing and debugging models
 - deploying and serving models
    
You can find more tutorials and resources on the official TensorFlow website: <https://www.tensorflow.org/>. Next We will dive more into real life tensorflow usages.