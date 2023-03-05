# learn-ml
My journey learning ML, scripts ordered as per progress.

I am following this book: AI and Machine Learning for Coders by Oreilly.

## Learning Order

1. I first ran a dummy script to test my Python install in PyCharm CE IDE. I expected it to come with Miniconda installed, but I had to install it myself.
2. Then I ran the test script given [here](https://developer.apple.com/metal/tensorflow-plugin/), this works by locally training the CIFAR100 dataset on a resnet50 network.


## Installation

I use a Mac with M1 Pro processor hence this installation was different from the typical steps.

1. Install Miniconda: `brew install miniconda`
2. Install dependencies: `conda install -c apple tensorflow-deps`
3. Install Tensorflow: `pip install tensorflow-macos==2.90`
4. Install GPU support: `pip install tensorflow-metal==0.5.0`

The reason I had to give a specific version here was because the default was some newer version which was giving errors. Hence using the latest versions documented [here](https://developer.apple.com/metal/tensorflow-plugin/).

