Overview
========

Deep learning with neural networks is accomplished through computation over dataflow graphs. Some frameworks (such as CNTK, Caffe2, Theano, and TensorFlow) make use of static graphs, while some (like PyTorch and Chainer) use dynamic graphs. All of these frameworks provide interfaces that make it simple for developers to construct computation graphs and runtimes that process graphs in an optimized way. The graphs serve as an intermediate representation (IR) that captures the intent of the developer's source code, and is conductive for optimization and translation to run on various devices (CPU, GPU, FPGA, etc.).

Why a common IR?
----------------

Today, each framework has its own proprietary representation of the graph, though they all provide similar capabilities. Consequently, each framework is an isolated stack of API, graph, and runtime. Furthermore, these frameworks are often optimized for some characteristic, such as fast training, supporting complex network architectures, inferencing on mobile devices, etc. When selecting a framework, it's up to the developer to choose the optimized characteristics that matters most to them. However, a framework optimized for a particular characteristic during research and development isn't always best suited for deployment. This problem leads to significant delays between the development and deployment stages because conversion is often necessary.

With the goal of democratizing AI, we envision developers being empowered to choose any framework that works best for their project, at any any stage of development and deployment. The Open Neural Network Exchange (ONNX) format is a common IR to establish this powerful ecosystem.

By providing a common representation of the computation graph, ONNX helps developers choose the right framework for their task, allows authors to focus on innovative enhancements, and enables hardware vendors to streamline optimizations for their platforms.

ONNX is design to be an open format. We welcome contributions from the community and encourage everyone to adopt ONNX in their ecosystem.
