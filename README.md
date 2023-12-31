# GAN-Anomaly-Detection
Anomaly detection using Generative Adversarial Network

### What is a [GAN](https://en.wikipedia.org/wiki/Generative_adversarial_network)?
- A generative adversarial network (GAN) is a machine learning model in which two neural networks compete with each other by using deep learning methods to become more accurate in their predictions.
- The two neural networks that make up a GAN are referred to as the generator and the discriminator. The generator is a convolutional neural network and the discriminator is a deconvolutional neural network. The goal of the generator is to artificially manufacture outputs that could easily be mistaken for real data. The goal of the discriminator is to identify which of the outputs it receives have been artificially created.
- These two networks are in a constant feedback loop, with the generator striving to create increasingly convincing data, and the discriminator becoming more adept at telling real from fake. The training continues until a point where the generator creates data that is nearly indistinguishable from real data, or when it achieves a satisfactory level of performance.

### How GAN is used in anomaly detection
1. In the training phase, you first train a GAN on a dataset containing only normal or non-anomalous data. The GAN's generator learns to model the underlying distribution of the normal data, producing data points that resemble the training dataset.
2.  After the GAN is trained on normal data, you can use it to generate synthetic data samples. To detect anomalies, you evaluate how well the generator can recreate a given data point. The idea is that if a data point is normal, the GAN should be able to generate something very similar to it, but if it's an anomaly, the generated sample will likely be significantly different.
3.  Calculate a discrepancy score between the original data point and the corresponding synthetic data generated by the GAN. Various methods like mean squared error or distance metrics can be used.
4.  Set a threshold on the anomaly scores. Data points with anomaly scores above this threshold are considered anomalies, while those below it are classified as normal.

The key idea in GAN-based anomaly detection is that anomalies will have higher anomaly scores because the generator struggles to produce data similar to them, whereas normal data points will have lower scores since they can be recreated more faithfully.


## Dataset
In this project, i use [NAB dataset](https://www.kaggle.com/datasets/boltzmannbrain/nab) - Dataset, and scoring for detecting anomalies in streaming data.

There are over 50 labeled real-world and artificial timeseries data files plus a novel scoring mechanism for real-time applications.

From the present datasets, I picked up and analyzed **Twitter_volume_AAPL** from realTweets dataset. This dataset does not include actual anomaly point, so we need to refer to [NAB github repository](https://github.com/numenta/NAB/blob/master/labels/combined_windows.json)
