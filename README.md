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

![Mac GPU getting fully utilised](static/gpu_activity.png)

It is nice to see that the Mac GPU is getting used 100% for an ML task running in TensorFlow. Back in 2017 when I last tried these things out, this was not possible.

## Fashion MNIST with Dense Layers

Now we begin to work with greyscale images, here we will keep things simple and use a fully connected dense layer. The main thing to learn here is train vs test accuracy. Also figuring out a way to automatically stop training at certain point, this is introduced using callbacks.

![For Dense network, train vs test accuracy graph](static/fashion_mnist_dense.png)

Here we can see that the model is overfitting very quickly, just one epoch is enough for it to learn most of what there is. After that test accuracy is not really improving even after we are training for 50 epochs! Test accuracy peaked at around 88%.

## Fashion MNIST with Convolutional Neural Networks

Now the above layer with 128 densely connected nodes is prefixed with a CNN feature extractor. Here again we will do the same exercise as above and see how much generalisation we can achieve - that is better accuracy on test set.

![For CNN, train vs test accuracy graph](static/fashion_mnist_cnn.png)

As you can see training set easily goes up to 99% (the model is rote-learned the data) but on testing set the gains are visible. Test accuracy in this case now peaks at 91%.