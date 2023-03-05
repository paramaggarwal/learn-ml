# learn-ml
My journey learning ML, scripts ordered as per progress.

I am following this book: AI and Machine Learning for Coders by Oreilly.

## Setting Up

I use a Mac with M1 Pro processor hence this installation was different from the typical steps.

1. Install Miniconda: `brew install miniconda`
2. Install dependencies: `conda install -c apple tensorflow-deps`
3. Install Tensorflow: `pip install tensorflow-macos==2.90`
4. Install GPU support: `pip install tensorflow-metal==0.5.0`

The reason I had to give a specific version here was because the default was some newer version which was giving errors. Hence using the latest versions documented [here](https://developer.apple.com/metal/tensorflow-plugin/).

I also installed PyCharm CE to get comfortable with IDE environment. This was again done with Homebrew: `brew install pycharm-ce`.

## Testing Setup

When setting up PyCharm, it expected an installation of Conda so that I can create a Python interpreter. I had to install this manually with `brew install miniconda`. Then I ran the dummy script that it creates. I am running this both in VSCode to test my local terminal setup and also in PyCharm to test the IDE-driven setup.

I then ran the test script given [here](https://developer.apple.com/metal/tensorflow-plugin/), this works by locally training the CIFAR100 dataset on a Resnet50 network. I ran this both on local M1 Pro as well as Google Colab GPU. Surprisingly, the local took 57sec per epoch, while Colab took 43sec per run - I am impressed that the local run is able to keep up.

![Mac GPU getting fully utilised](static/Screenshot%202023-03-06%20at%2012.20.18%20AM.png)

It is nice to see that the Mac GPU is getting used 100% for an ML task running in TensorFlow. Back in 2017 when I last tried these things out, this was not possible.