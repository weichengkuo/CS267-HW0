## Name: Weicheng Kuo

## Student ID: 25941765

## Bio
I am a second-year PhD student (Class 2015) working with Prof. Jitendra Malik in the Vision group at University of California Berkeley. I graduated from National Taiwan University summa cum laude (top 1% in class). In addition, I was the Berkeley Graduate Fellowship recipient of EECS department. My current interests are Computer Vision and Machine learning, but I also have some journal publications in biomedical imaging and medical image analysis. In 2012, I worked as a summer business analyst at Mckinsey&Company. In summer 2015, I interned with Prof. William T Freeman and Ce Liu at Google Research. In summer 2016, I worked as a research intern at Apple to develop video analysis algorithm by unsupervised sequence learning techniques. Through this CS267 class, I'm hoping to learn more about how parallel computing can be applied to solve large-scale video analysis problem -- this includes the common paradigms of parallel algorithms and the hardware platforms for high performance.  

## Application: Large-Scale Video Analysis
In computer vision, video is always a challenging but interesting problem, because it has much more information than still images. For example, motion cues tell us a lot about the activities in the video that still images do not reveal. The challenge here is videos are much larger than still images. Take a 30 fps video for example. A one-minute recording then contains 1800 frames! Think about how many videos Youtube or Facebook process each day. In addition, robotics community are collecting all kinds of videos right now based on their sensory inputs. Scientists are collecting all sorts of time lapse data as well. The world is surely moving toward collecting more videos! Unfortunately, a naive way to run object detection on the aforementioned one-minute video would take about 1800s ~ 0.5 hour, but if we take advantage of parallel computing, we could be done in 1s! Due to the high parallelizability of video, I believe parallel computing will play increasingly important role in video processing down the road. 

Since most computer vision algorithms rely on deep learning nowadays, video analysis is no exception. Here's some background about deep learning. As its name suggests, deep learning typically involves a stack of neural network with a good amount of dense matrix multiplication. It's common for the network nowadays to be 100-layer deep and have millions of free parameters. More often than not, the input as well as output dimensions are high. That's why parallel computing is necessary for deep learning in practice.  

Often the computation is executed on GPUs, because of they are suited for matrix operations. Many libraries have been developed to facilitate deep learning research including Caffe by Berkeley, Tensoflow by Google, Torch by Facebook, and Theano by University of Montreal. These libraries provide interface between high-level APIs and CUDA, so that users can focus on network design without worrying about GPU programming. In addition, they also enable multi-GPU training of networks by model or data parallelisms. Model parallelism splits the large model on multiple GPUs and have them communicate with each other, while data parallelism feed different data to the GPUs and aggregate the gradients. When the model is large, model-parallelism is necessary. Otherwise, data-parallelism is usually preferred. 

In 2012, AlexNet came out with stunning results on ImageNet, which most considered to be the start of this wave of deep learning revolution. Shortly after that, there came a Google paper on distributed learning of deep networks. The group implemented two algrotihms to achieve 30x speedup compared to single machine while maintaining the same performance -- 1) An asynchronous stochastic gradient descent that support large number of model replicas, and 2) Sandblaster, a framework that supports distributed batch optimization algorithms like L-BFGS. Building upon this work, Tensorflow (also by Google) [x] describes network computations by a graph dataflow-like model and maps them to a wide variety of platforms -- from mobile phone to single machine to large-scale clusters. This modification proves to be a great success and is widely adopted by the industry and academia now. 

##Reference
1. Krizhevsky, Alex, Ilya Sutskever, and Geoffrey E. Hinton. "Imagenet classification with deep convolutional neural networks." Advances in neural information processing systems. 2012.
2. Dean, Jeffrey, et al. "Large scale distributed deep networks." Advances in neural information processing systems. 2012.
3. Abadi, Martín, et al. "Tensorflow: Large-scale machine learning on heterogeneous distributed systems." arXiv preprint arXiv:1603.04467 (2016). 






