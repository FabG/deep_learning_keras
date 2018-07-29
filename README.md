Deep Learnning with Python, Keras and Pytorch

##Intro
###TensorFlow
The most popular deep learning framework that offers a Python Application Programming Interface (API) is [TensorFlow](https://www.tensorflow.org/). 
TensorFlow was open sourced by Google in 2015 and it contains a bunch of awesome tools that makes machine learning and deep learning projects easier to execute. 
It is also worth mentioning that there are other frameworks such as Theano, Pytorch, MXNet, Chainer etc which are widely used.


###Keras
[Keras](https://keras.io/)  is a high-level neural networks API, written in Python and capable of running on top of TensorFlow, CNTK, or Theano. It was developed with a focus on enabling fast experimentation. 
Being able to go from idea to result with the least possible delay is key to doing good research.

The advantage of using Keras is that it provides an easy API for building convolutional and recurrent neural networks. 
It also provides these building blocks in such a form that different kinds of models can be constructed such as multi-input models, multi-output models etc. 
It also allows for advanced features such as weight sharing and model sharing. One important design philosophy of Keras is that the same code can be run on CPUs and GPUs without any modification whatsoever. 
It is because of these perks that Keras is popular among deep learning practitioners as it focuses on modularity and scalability. 
In this github repo, we would use Keras with TensorFlow as the backend. 
Keras is compatible with TensorFlow and models developed in Keras can easily be exported to TensorFlow.



###Install Python (via Anaconda) + TensorFlow and Keras / OPTION 1
I strongly recommend installing Python, NumPy through [Anaconda Distribution](https://www.anaconda.com/)
Anaconda is a free and open-source software distribution for data science. In a nutshell, it's an up-to-date, comprehensive bundle of the most popular tools and libraries in this field and enables you to dive in quickly and easily.
By downloading Anaconda, you get conda, Python, Jupyter Notebook and hundreds of other open source packages.

The installer comes with the core libraries for data science to get you up and running immediately. 
In addition, Anaconda includes a language-agnostic package manager called conda that enables you to add more libraries later.
As the cherry on top, conda is also a top-notch virtual environment manager, so you don't need virtualenv or venv. 

1. Create a virtual environment (optionally - these should be one by default called 'base')
```
conda create --name deeplearning python
```
It will install a bunch of new packages in that virtual environment such as pip, python, openssl,...

To activate this environment, use:
```
 > conda activate deeplearning
```
To activate the base environment, use:
```
  > conda activate 
```

To deactivate an active environment, use:
```
> conda deactivate
```


After activation, notice the prompt is now flanked by the name of the environment in parentheses—this indicates you're inside.
In my case:
```
(deeplearning) Fab@MacBookAir-Fab-Perso:~$
```

Earlier, the Anaconda installer automatically created a conda environment called root that houses the core libraries for data science. Since we've now moved into a different environment, we can't access those libraries unless we re-install them and their dependencies in the new environment. Fortunately, we can use conda to install a few packages that cover everything we need. Because I make heavy use of the core data science libraries, I installed every package listed below. Make sure to install them in order listed below; only Seaborn and Scikit-learn are optional.

IPython and Jupyter are a must for those who rely on Jupyter notebooks for data science (who doesn't?).

```
conda install ipython
conda install jupyter
```

Pandas includes the de facto library for exploratory analysis and data wrangling in Python.
```
conda install pandas
```

SciPy is an exhaustive package for scientific computing, but the namesake library itself is a dependency for Keras.
```
conda install scipy
```

Seaborn is a great high-level visualization library. If you're still exclusively using Matplotlib for plotting, do yourself a favor and take a look.
```
conda install seaborn
```

Scikit-learn contains the go-to library for machine learning tasks in Python outside of neural networks.

```
conda install scikit-learn
```




 Conda Cheat Sheet
 ```
   # update conda in your default environment 
   $ conda upgrade conda
   $ conda upgrade --all
   
   # create a new environment with conda
   $ conda create -n [my-env-name]
   
   # activate the environment you created
   $ source activate [my-env-name]
   
   # take a look at the environment you created
   $ conda info
   $ conda list
   
   # install a package with conda and verify it's installed
   $ conda install numpy
   $ conda list
   
   # take a look at the list of environments you currently have
   $ conda info -e
   
   # remove an environment
   $ conda env remove --name [my-env-name]
```



2. Install TensorFlow
Notes: neither library is officially available via a conda package (yet) so we'll need to install them with pip.
TensorFlow install steps are available here: [Tensorflow install](https://www.tensorflow.org/install/install_mac)

Update: you no longer need to install Keras separately since it is part of the core TensorFlow API. 
“import tensorflow as tf” then use tf.keras in your code. 
You will notice the strikethrough of any mention of Keras installation in this blog post


```
# optionally install pip in the virtual environment if not installed already. It should.
$ conda install pip
$ pip install --upgrade pip

# alternative: $easy_install -U pip

# check version of pythn used first
$ conda list | grep python

# install Tensorflow
$ pip install --upgrade tensorflow # for python 2.7
$ pip3 install --upgrade tensorflow # for python 3.*

~~# install Keras (Note: please install TensorFlow first)~~
~~$pip install --upgrade keras~~
```

Notes: if you have an error when installing TensorFlow as I had because of grpc, you can specify the version.
For reference, the issue I had qas 
> targeted OS version does not support use of thread local variables in __ZL19iomgr_platform_initv for architecture x86_64
The below worked for me:
> File "/private/var/folders/hg/n2vgnkvx50b_ndyf6j_c_dkw0000gn/T/pip-install-6_088B/grpcio/setup.py", line 347, in <module>
> ...
> error code 1 in /private/var/folders/hg/n2vgnkvx50b_ndyf6j_c_dkw0000gn/T/pip-install-6_088B/grpcio/

```
$ pip install grpcio==1.9.1 --upgrade tensorflow
```

###Install Python with VirtualEnv + TensorFlow + Keras  / OPTION 2

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








### Sources:
 - Kindle Book Pan, Chao. Deep Learning With Python: Step By Step Guide With Keras and Pytorch 
 - Web articles: 
 https://elitedatascience.com/keras-tutorial-deep-learning-in-python
 http://inmachineswetrust.com/posts/deep-learning-setup/
 https://medium.com/@margaretmz/anaconda-jupyter-notebook-tensorflow-and-keras-b91f381405f8
 
 