Deep Learnning with Python, Keras and Pytorch
Based on book:
Pan, Chao. Deep Learning With Python: Step By Step Guide With Keras and Pytorch 

##Intro
###TensorFlow
The most popular deep learning framework that offers a Python Application Programming Interface (API) is TensorFlow. 
TensorFlow was open sourced by Google in 2015 and it contains a bunch of awesome tools that makes machine learning and deep learning projects easier to execute. 
It is also worth mentioning that there are other frameworks such as Theano, Pytorch, MXNet, Chainer etc which are widely used.


###Keras
The advantage of using Keras is that it provides an easy API for building convolutional and recurrent neural networks. 
It also provides these building blocks in such a form that different kinds of models can be constructed such as multi-input models, multi-output models etc. 
It also allows for advanced features such as weight sharing and model sharing. One important design philosophy of Keras is that the same code can be run on CPUs and GPUs without any modification whatsoever. 
It is because of these perks that Keras is popular among deep learning practitioners as it focuses on modularity and scalability. 
In this github repo, we would use Keras with TensorFlow as the backend. 
Keras is compatible with TensorFlow and models developed in Keras can easily be exported to TensorFlow.



###Install TensorFlow and Keras
TensorFlow install teps are available here: [Tensorflow install](https://www.tensorflow.org/install/install_mac)

For this repo, since I use a MAC, I include install steps for MAC OS and for Python 2.7

I recommend using **VirtualEnv**  that is a virtual Python environment isolated from other Python development, incapable of interfering with or being affected by other Python programs on the same machine. 
During the Virtualenv installation process, you will install not only TensorFlow but also all the packages that TensorFlow requires. 
To start working with TensorFlow, you simply need to "activate" the virtual environment. 
All in all, Virtualenv provides a safe and reliable mechanism for installing and running TensorFlow.

1. Start a terminal (a shell). You'll perform all subsequent steps in this shell.

2. Install pip and Virtualenv by issuing the following commands:

```
$ sudo easy_install pip
$ pip install --upgrade virtualenv 
```

3. Create a Virtualenv environment by issuing the following command:: 
```
$ virtualenv --system-site-packages ~/tensorflow
```

4. Activate the Virtualenv environment by issuing the following command:

```
$ cd ~/tensorflow
$ source ./bin/activate
(tensorflow) Fab@MacBookAir-Fab-Perso:~/tensorflow$
```

Notes: When you are done using TensorFlow, you may deactivate the environment by issuing the following command:
```       
(tensorflow)$ deactivate 
```

5. Issue the below commands to install TensorFlow and all the packages that TensorFlow requires into the active Virtualenv environment:
```
(tensorflow) Fab@MacBookAir-Fab-Perso:~/tensorflow$
(tensorflow) Fab@MacBookAir-Fab-Perso:~/tensorflow$ easy_install -U pip
(tensorflow) Fab@MacBookAir-Fab-Perso:~/tensorflow$ pip install --upgrade tensorflow
```

To check if TensorFlow is successfully installed, run:
```
$ python -c 'import tensorflow as tf; print(tf.__version__)'
1.3.0
```
In this case it tells me I have TensorFlow version 1.3

6. Install Keras
```
$ pip install keras
```

If you have an error message as I had:
> here was a problem confirming the ssl certificate: [SSL: TLSV1_ALERT_PROTOCOL_VERSION] tlsv1 alert protocol version (_ssl.c:590) - skipping


Try to upgrade pip without running pip as follow
```
$ curl https://bootstrap.pypa.io/get-pip.py | python
```

To check if Keras is successfully installed, run:
```
$ python -c 'import keras; print(keras.__version__)'
Using TensorFlow backend.
2.2.2
```
In this case it tells me I have Keras version 2.2.2

