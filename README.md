<p align="center"><img src="images/logo.png" width="100%"/></p>

***

<p align="center">
:orange_book: List of real-world AI infrastructures (a.k.a., <strong>machine
learning systems, pipelines, workflows</strong>, and <strong>platforms</strong>)
for machine/deep learning training and/or inference <strong>in
production</strong> :electric_plug:. This usually includes technology stack
necessary to enable machine learning algorithms run in production environments
in a stable, scalable and reliable way. The list is for my own learning purposes,
but feel free to <strong>contribute</strong> / star / fork / pull request. Any
recommendations and suggestions are welcome :tada:.
</p>

***

# Introduction

This list contains some popular actively-maintained AI infrastructures that
focus on one or more of the following topics:

- Architecture of **end-to-end** machine learning training **pipelines**.
- **Inference** at scale in production on Cloud :cloud: or on end devices :iphone:.
- **Compiler and optimization** stacks for deployments on variety of devices.
- Novel ideas of efficient large-scale **distributed training**.

in **no specific order**. This list cares more about overall architectures of AI
solutions in production instead of individual machine/deep learning training or
inference frameworks. My learning goals are: understand the workflows and
principles of how to build (large-scale) systems that can enable machine
learning in production.

# Platforms

### [TFX](https://www.tensorflow.org/tfx/) - TensorFlow Extended ([Google](https://www.google.com/about/))

> TensorFlow Extended (TFX) is a [TensorFlow](https://www.tensorflow.org/)-based general-purpose machine learning platform implemented at Google.

| [__homepage__](https://www.tensorflow.org/tfx/) | [__talk__](https://www.youtube.com/watch?v=vdG7uKQ2eKk) | [__paper__](https://dl.acm.org/citation.cfm?id=3098021) |

#### Architecture:

<p align="center"><img src="images/google-tfx-arch.png" width="90%"/></p>

#### Components:

- **TensorFlow Data Validation**: a library for exploring and validating machine learning data.

- **TensorFlow Transformation**: perform full-pass analyze phases over data to create transformation graphs that are consistently applied during training and serving.

- **TensorFlow Model Analysis**: libraries and visualization components to compute full-pass and sliced model metrics over large datasets, and analyze them in a notebook.

- **TensorFlow Serving**: a flexible, high-performance serving system for machine learning models, designed for production environments

### [Kubeflow](https://www.kubeflow.org/) - The Machine Learning Toolkit for [Kubernetes](https://kubernetes.io/) ([Google](https://www.google.com/about/))

> The Kubeflow project is dedicated to making deployments of machine learning (ML) workflows on [Kubernetes](https://kubernetes.io/) simple, portable and scalable. Our goal is not to recreate other services, but to provide a straightforward way to deploy best-of-breed open-source systems for ML to diverse infrastructures. Anywhere you are running [Kubernetes](https://kubernetes.io/), you should be able to run Kubeflow.

> Kubeflow started as an open sourcing of the way Google ran [TensorFlow](https://www.tensorflow.org/) internally, based on a pipeline called TensorFlow Extended.

| [__homepage__](https://www.kubeflow.org/) | [__github__](https://github.com/kubeflow/kubeflow) | [__documentation__](https://www.kubeflow.org/docs/about/kubeflow/) |
[__blog__](https://kubernetes.io/blog/2017/12/introducing-kubeflow-composable/) |
[__talk__](https://conferences.oreilly.com/strata/strata-ny-2018/public/schedule/detail/69041) | [__slices__](https://cdn.oreillystatic.com/en/assets/1/event/278/Kubeflow%20explained_%20Portable%20machine%20learning%20on%20Kubernetes%20Presentation.pdf) |

#### Components:

- **Notebooks**: a JupyterHub to create and manage interactive Jupyter notebooks.

- **TensorFlow Model Training**: a TensorFlow Training Controller that can be configured to use either CPUs or GPUs and be dynamically adjusted to the size of a cluster with a single setting.

- **Model Serving**: a TensorFlow Serving container to export trained TensorFlow models to [Kubernetes](https://kubernetes.io/). Integrated with Seldon Core, an open source platform for deploying machine learning models on [Kubernetes](https://kubernetes.io/), and NVIDIA TensorRT Inference Server for maximized GPU utilization when deploying ML/DL models at scale.

- **Multi-Framework**: includes [TensorFlow](https://www.tensorflow.org/), [PyTorch](https://pytorch.org/), [MXNet](https://mxnet.apache.org/), [Chainer](https://chainer.org/), and more.

### RAPIDS - Open GPU Data Science ([NVIDIA](https://www.nvidia.com/en-us/))

> The RAPIDS suite of open source software libraries gives you the freedom to execute end-to-end data science and analytics pipelines entirely on GPUs. It relies on NVIDIA® CUDA® primitives for low-level compute optimization, but exposes that GPU parallelism and high-bandwidth memory speed through user-friendly Python interfaces.

> RAPIDS is the result of contributions from the machine learning community and [GPU Open Analytics Initiative (GOAI)](http://gpuopenanalytics.com/) partners, such as [Anaconda](https://www.anaconda.com/), [BlazingDB](https://blazingdb.com/), [__Gunrock__](https://github.com/gunrock/gunrock), etc.

| [__homepage__](https://rapids.ai/) | [__blog__](https://medium.com/rapids-ai) | [__github__](https://github.com/RAPIDSai) |

#### Architecture:

<p align="center"><img src="images/nvidia-rapids-arch.png" width="80%"/></p>

#### Components:

- **[Apache Arrow](https://arrow.apache.org/)**: a columnar, in-memory data structure that delivers efficient and fast data interchange with flexibility to support complex data models.

- **cuDF**: a DataFrame manipulation library based on [Apache Arrow](https://arrow.apache.org/) that accelerates loading, filtering, and manipulation of data for model training data preparation. The Python bindings of the core-accelerated CUDA DataFrame manipulation primitives mirror the pandas interface for seamless onboarding of pandas users.

- **cuML**: a collection of GPU-accelerated machine learning libraries that will provide GPU versions of all machine learning algorithms available in [scikit-learn](https://scikit-learn.org/).

- **cuGRAPH**: a framework and collection of graph analytics libraries that seamlessly integrate into the RAPIDS data science platform.

- **Deep Learning Libraries**: data stored in [Apache Arrow](https://arrow.apache.org/) can be seamlessly pushed to deep learning frameworks that accept array_interface such as [PyTorch](https://pytorch.org/) and [Chainer](https://chainer.org/).

- **Visualization Libraries**: RAPIDS will include tightly integrated data visualization libraries based on [Apache Arrow](https://arrow.apache.org/). Native GPU in-memory data format provides high-performance, high-FPS data visualization, even with very large datasets.

### Michelangelo - Uber's Machine Learning Platform ([Uber](https://www.uber.com/))

> Michelangelo, an internal ML-as-a-service platform that democratizes machine learning and makes scaling AI to meet the needs of business as easy as requesting a ride.

> Michelangelo consists of a mix of open source systems and components built in-house. The primary open sourced components used are [HDFS](https://hortonworks.com/apache/hdfs/), [Spark](https://spark.apache.org/), [Samza](http://samza.apache.org/), [Cassandra](http://cassandra.apache.org/), [MLLib](https://spark.apache.org/mllib/), [XGBoost](https://github.com/dmlc/xgboost), and [TensorFlow](https://www.tensorflow.org/).

| [__blog__](https://eng.uber.com/michelangelo/) | [__use-cases__](https://eng.uber.com/scaling-michelangelo/) |

#### Architecture:

<p align="center"><img src="images/uber-michelangelo-arch.png" width="90%"/></p>

#### Components:

- Manage data
- Train models
- Evaluate models
- Deploy models
- Make predictions
- Monitor predictions

### COTA: Improving Uber Customer Care with NLP & Machine Learning ([Uber](https://www.uber.com/))

> COTA, our Customer Obsession Ticket Assistant, a tool that uses machine learning and natural language processing (NLP) techniques to help agents deliver better customer support. Leveraging our Michelangelo machine learning-as-a-service platform on top of our customer support platform

| [__blog__](https://eng.uber.com/cota/) |

#### Architecture:

<p align="center"><img src="images/uber-cota-arch.png" width="90%"/></p>

#### Components:

- Preprocessing
- Topic modeling
- Feature engineering
- Pointwise ranking algorithm


### FBLearner ([Facebook](https://www.facebook.com/))

> FBLearner Flow is capable of easily reusing algorithms in different products, scaling to run thousands of simultaneous custom experiments, and managing experiments with ease.

| [__blog__](https://code.fb.com/core-data/introducing-fblearner-flow-facebook-s-ai-backbone/) | [__slices__](https://www.matroid.com/scaledml/2018/yangqing.pdf) | [__talk__](https://atscaleconference.com/videos/machine-learning-at-scale-fblearner-flow/) |

#### Architecture:

<p align="center"><img src="images/facebook-fblearnerflow-arch.png" width="90%"/></p>

#### Components:

- Experimentation Management UI
- Launching Workflows
- Visualizing and Comparing Outputs
- Managing Experiments
- Machine Learning Library

### Alchemist ([Apple](https://www.apple.com/))

> Alchemist - an internal service built at Apple from the ground
up for easy, fast, and scalable distributed training.

| [__paper__](https://arxiv.org/abs/1811.00143) |

#### Architecture:

<p align="center"><img src="images/apple-alchemist-arch.png" width="70%"/></p>

#### Components:

- **UI Layer**: command line interface (CLI) and a web UI.

- **API Layer**: exposes services to users, which
allows them to upload and browse the code assets, submit distributed jobs, and query the logs and metrics.

- **Compute Layer**: contains the compute-intensive workloads; in particular, the training and evaluation tasks orchestrated by the job scheduler.

- **Storage Layer**: contains the distributed file systems and object storage systems that maintain the training and evaluation datasets, the trained model artifacts, and the code assets.

### FfDL - Fabric for Deep Learning ([IBM](https://www.ibm.com/))

> Deep learning frameworks such as [TensorFlow](https://www.tensorflow.org/), [PyTorch](https://pytorch.org/), Caffe, Torch, Theano, and MXNet have contributed to the popularity of deep learning by reducing the effort and skills needed to design, train, and use deep learning models. Fabric for Deep Learning (FfDL, pronounced “fiddle”) provides a consistent way to run these deep-learning frameworks as a service on **[Kubernetes](https://kubernetes.io/)**.

| [__blog__](https://developer.ibm.com/code/open/projects/fabric-for-deep-learning-ffdl/) | [__github__](https://github.com/IBM/FfDL) |

#### Architecture:

<p align="center"><img src="images/ibm-ffdl-arch-2.png" width="90%"/></p>

#### Components:

- **REST API**: the REST API microservice handles REST-level HTTP requests and acts as proxy to the lower-level gRPC Trainer service.

- **Trainer**: the Trainer service admits training job requests, persisting metadata and model input configuration in a database (MongoDB).

- **Lifecycle Manager and learner pods**: The Lifecycle Manager (LCM) deploys training jobs arriving from the Trainer, halting (pausing) and terminating training jobs. LCM uses the [Kubernetes](https://kubernetes.io/) cluster manager to deploy containerized training jobs.

- **Training Data Service**: The Training Data Service (TDS) provides short-lived storage and retrieval for logs and evaluation data from a Deep Learning training job.

### BigDL - Distributed Deep Learning Library for Apache Spark ([Intel](https://www.intel.com/content/www/us/en/homepage.html))

> BigDL is a distributed deep learning library for **Apache Spark**; with BigDL, users can write their deep learning applications as standard Spark programs, which can directly run on top of existing Spark or Hadoop clusters. To makes it easy to build Spark and BigDL applications, a high level [Analytics Zoo](https://github.com/intel-analytics/analytics-zoo) is provided for end-to-end analytics + AI pipelines.

 | [__blog__](https://software.intel.com/en-us/articles/bigdl-distributed-deep-learning-on-apache-spark) | [__code__](https://github.com/intel-analytics/BigDL) |

#### Architecture:

<p align="center"><img src="images/intel-bigdl-arch.png" width="90%"/></p>

#### Components:

- **Rich deep learning support**. Modeled after Torch, BigDL provides comprehensive support for deep learning, including numeric computing (via Tensor) and high level neural networks; in addition, users can load pre-trained Caffe or Torch models into Spark programs using BigDL.

- **Extremely high performance**. To achieve high performance, BigDL uses Intel MKL and multi-threaded programming in each Spark task. Consequently, it is orders of magnitude faster than out-of-box open source Caffe, Torch or [TensorFlow](https://www.tensorflow.org/) on a single-node Xeon (i.e., comparable with mainstream GPU).

- **Efficiently scale-out**. BigDL can efficiently scale out to perform data analytics at "Big Data scale", by leveraging Apache Spark (a lightning fast distributed data processing framework), as well as efficient implementations of synchronous SGD and all-reduce communications on Spark.

### SageMaker ([Amazon Web Service](https://aws.amazon.com/?nc2=h_lg))

> Amazon SageMaker is a fully-managed platform that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. Amazon SageMaker removes all the barriers that typically slow down developers who want to use machine learning.

| [__blog__](https://aws.amazon.com/sagemaker/) | [__talk__](https://youtu.be/lM4zhNO5Rbg) |

#### Architecture:

<p align="center"><img src="images/amazon-sagemaker-arch.png" width="90%"/></p>

### TransmogrifAI ([Salesforce](https://www.salesforce.com/))

> TransmogrifAI (pronounced trăns-mŏgˈrə-fī) is an AutoML library written in Scala that runs on top of Spark. It was developed with a focus on enhancing machine learning developer productivity through machine learning automation, and an API that enforces compile-time type-safety, modularity and reuse.

| [__homepage__](https://transmogrif.ai/) | [__github__](https://github.com/salesforce/TransmogrifAI) | [__documentation__](https://docs.transmogrif.ai/en/stable/) | [__blog__](https://engineering.salesforce.com/open-sourcing-transmogrifai-4e5d0e098da2) |

#### Architecture:

<p align="center"><img src="images/salesforce-transmogrifai-arch.png" width="90%"/></p>

#### Components:

- Build production ready machine learning applications in hours, not months.

- Build machine learning models.

- Build modular, reusable, strongly typed machine learning workflows.

### NNI - Neural Network Intelligence ([Microsoft](https://www.microsoft.com/en-us/))

> NNI (Neural Network Intelligence) is a toolkit to help users run automated machine learning (AutoML) experiments. The tool dispatches and runs trial jobs generated by tuning algorithms to search the best neural architecture and/or hyper-parameters in different environments like local machine, remote servers and cloud.

| [__homepage__](https://nni.readthedocs.io/en/latest/index.html) | [__github__](https://github.com/Microsoft/nni) |

#### Architecture:

<p align="center"><img src="images/microsoft-nni-arch.png" width="90%"/></p>

#### Components:

- **Experiment**: An experiment is one task of, for example, finding out the best hyperparameters of a model, finding out the best neural network architecture. It consists of trials and AutoML algorithms.

- **Search Space**: It means the feasible region for tuning the model. For example, the value range of each hyperparameters.

- **Configuration**: A configuration is an instance from the search space, that is, each hyperparameter has a specific value.

- **Trial**: Trial is an individual attempt at applying a new configuration (e.g., a set of hyperparameter values, a specific nerual architecture). Trial code should be able to run with the provided configuration.

- **Tuner**: Tuner is an AutoML algorithm, which generates a new configuration for the next try. A new trial will run with this configuration.

- **Assessor**: Assessor analyzes trial’s intermediate results (e.g., periodically evaluated accuracy on test dataset) to tell whether this trial can be early stopped or not.

- **Training Platform**: It means where trials are executed. Depending on your experiment’s configuration, it could be your local machine, or remote servers, or large-scale training platform (e.g., OpenPAI, Kubernetes).

### Auto-Keras

> Auto-Keras is an open source software library for automated machine learning (AutoML). It is developed by DATA Lab at Texas A&M University and community contributors. The ultimate goal of AutoML is to provide easily accessible deep learning tools to domain experts with limited data science or machine learning background. Auto-Keras provides functions to automatically search for architecture and hyperparameters of deep learning models.

| [__homepage__](https://autokeras.com/) | [__github__](https://github.com/jhfjhfj1/autokeras) | [__paper__](https://arxiv.org/abs/1806.10282) |

#### Architecture:

<p align="center"><img src="images/autokeras-arch.png" width="60%"/></p>

### MLFlow ([Databricks](https://databricks.com/))

> MLflow is an open source platform for managing the end-to-end machine learning lifecycle.

| [__homepage__](https://mlflow.org/) | [__github__](https://github.com/mlflow/mlflow) |  [__documentation__](https://mlflow.org/docs/latest/index.html) | [__blog__](https://databricks.com/blog/2018/06/05/introducing-mlflow-an-open-source-machine-learning-platform.html) |

#### Architecture:

<p align="center"><img src="images/databricks-mlflow-arch.png" width="90%"/></p>

#### Components:

- **MLflow Tracking**: tracking experiments to record and compare parameters and results.

- **MLflow Projects**: packaging ML code in a reusable, reproducible form in order to share with other data scientists or transfer to production.

- **MLflow Models**: managing and deploying models from a variety of ML libraries to a variety of model serving and inference platforms.

### [H2O](https://www.h2o.ai/) - Open Source, Distributed Machine Learning for Everyone

> H2O is a fully open source, distributed in-memory machine learning platform with linear scalability. H2O’s supports the most widely used statistical & machine learning algorithms including gradient boosted machines, generalized linear models, deep learning and more. H2O also has an industry leading AutoML functionality that automatically runs through all the algorithms and their hyperparameters to produce a leaderboard of the best models.

> H2O4GPU is an open source, GPU-accelerated machine learning package with APIs in Python and R that allows anyone to take advantage of GPUs to build advanced machine learning models. A variety of popular algorithms are available including Gradient Boosting Machines (GBM’s), Generalized Linear Models (GLM’s), and K-Means Clustering. Our benchmarks found that training machine learning models on GPUs was up to 40x faster than CPU based systems.

| [__h2o__](https://www.h2o.ai/products/h2o/) | [__h2o4gpu__](https://www.h2o.ai/products/h2o4gpu/) |

<p align="center"><img src="images/h2o-arch.png" width="80%"/></p>

### Project Ray ([RISELab](https://rise.cs.berkeley.edu/projects/ray/))

> Ray is a high-performance distributed execution framework targeted at large-scale machine learning and reinforcement learning applications. It achieves scalability and fault tolerance by abstracting the control state of the system in a global control store and keeping all other components stateless. It uses a shared-memory distributed object store to efficiently handle large data through shared memory, and it uses a bottom-up hierarchical scheduling architecture to achieve low-latency and high-throughput scheduling. It uses a lightweight API based on dynamic task graphs and actors to express a wide range of applications in a flexible manner.

| [__homepage__](https://ray.readthedocs.io/en/latest/) | [__github__](https://github.com/ray-project/ray) | [__blog__](https://ray-project.github.io/) | [__design overview__](https://ray.readthedocs.io/en/latest/internals-overview.html) | [__paper__](https://arxiv.org/abs/1712.05889) |

#### Architecture:

<p align="center"><img src="images/ucb-ray-arch.png" width="70%"/></p>

#### Components:

- **Tune**: Scalable hyper-parameter search.

- **RLlib**: Scalable reinforcement learning.

- **Distributed** training.

### Angel ([Tencent](https://www.tencent.com/en-us/))

> **Angel** is a high-performance distributed machine learning platform based on the philosophy of **Parameter Server**. It is tuned for performance with big data from Tencent and has a wide range of applicability and stability, demonstrating increasing advantage in handling higher dimension model. Angel is jointly developed by Tencent and Peking University, taking account of both high availability in industry and innovation in academia.

> With **model-centered** core design concept, Angel partitions parameters of complex models into multiple parameter-server nodes, and implements a variety of machine learning algorithms using efficient model-updating interfaces and functions, as well as flexible consistency model for synchronization. Angel is developed with **Java** and **Scala**. It supports running on **Yarn**. With PS Service abstraction, it supports **Spark** on Angel.

| [__github__](https://github.com/Angel-ML/angel) | [__documentation__](https://github.com/Angel-ML/angel/blob/master/README_en.md) | [__paper__](http://net.pku.edu.cn/~cuibin/Papers/2017NSRangel.pdf) |

#### Architecture:

<p align="center"><img src="images/tencent-angel-arch.png" width="90%"/></p>

#### Components:

- **Parameter Server Layer**: provide flexible and multi-framework PS responsible for distributed model storage, communication synchronization and coordination of computing.

- **Worker Layer**: satisfy needs for algorithm development and innovation which automatically read and partition data and compute model delta locally. It communicate with the PS Server to complete the model training and prediction process.

- **Model Layer**: provide necessary functions of PS and support targeted optimization for performance. It hosts functionalities such as model pull/push operations, multiple sync protocols, model partitioner, etc. This layer bridges between the worker layer and the PS layer.

# Deployment and Optimizations

### CoreML ([Apple](https://www.apple.com/))

> Integrate machine learning models into your app. Core ML is the foundation for domain-specific frameworks and functionality. Core ML supports Vision for image analysis, Natural Language for natural language processing, and GameplayKit for evaluating learned decision trees. Core ML itself builds on top of low-level primitives like Accelerate and BNNS, as well as Metal Performance Shaders.

> Core ML is optimized for on-device performance, which minimizes memory footprint and power consumption. Running strictly on the device ensures the privacy of user data and guarantees that your app remains functional and responsive when a network connection is unavailable.

| [__homepage__](https://developer.apple.com/machine-learning/) | [__documentation__](https://developer.apple.com/documentation/coreml) | [__resources__](https://developer.apple.com/machine-learning/build-run-models/) |

<p align="center"><img src="images/apple-coreml-arch.png" width="70%"/></p>

### TensorFlow Lite ([Google](https://www.google.com/about/))

> TensorFlow Lite is the official solution for running machine learning models on mobile and embedded devices. It enables on‑device machine learning inference with low latency and a small binary size on Android, iOS, and other operating systems.

| [__homepage__](https://www.tensorflow.org/lite/) | [__blog__](https://developers.googleblog.com/2017/11/announcing-tensorflow-lite.html) |

#### Architecture:

<p align="center"><img src="images/google-tflite-arch.jpg" width="90%"/></p>

#### Components:

- **TensorFlow Model**: A trained TensorFlow model saved on disk.

- **TensorFlow Lite Converter**: A program that converts the model to the TensorFlow Lite file format.

- **TensorFlow Lite Model File**: A model file format based on FlatBuffers, that has been optimized for maximum speed and minimum size.

### [TensorRT](https://developer.nvidia.com/tensorrt) ([NVIDIA]())

> NVIDIA TensorRT™ is a platform for high-performance deep learning inference. It includes a deep learning inference optimizer and runtime that delivers low latency and high-throughput for deep learning inference applications.

| [__homepage__](https://developer.nvidia.com/tensorrt) | [__blog__](https://devblogs.nvidia.com/speed-up-inference-tensorrt/) | [__documentation__](https://docs.nvidia.com/deeplearning/sdk/tensorrt-developer-guide/index.html) | [__benchmark__](https://developer.nvidia.com/deep-learning-performance-training-inference#deeplearningperformance_inference) |
#### Architecture:

<p align="center"><img src="images/nvidia-tensorrt-arch.png" width="90%"/></p>

#### Components:

- **Weight & Activation Precision Calibration**: Maximizes throughput by quantizing models to INT8 while preserving accuracy.

- **Layer & Tensor Fusion**: Optimizes use of GPU memory and bandwidth by fusing nodes in a kernel.

- **Kernel Auto-Tuning**: Selects best data layers and algorithms based on target GPU platform.

- **Dynamic Tensor Memory**: Minimizes memory footprint and re-uses memory for tensors efficiently.

- **Multi-Stream Execution**: Scalable design to process multiple input streams in parallel.

### [Greengrass](https://aws.amazon.com/greengrass/) ([Amazon](https://aws.amazon.com/?nc2=h_lg))

> AWS Greengrass is software that lets you run local compute, messaging, data caching, sync, and ML inference capabilities for connected devices in a secure way. With AWS Greengrass, connected devices can run AWS Lambda functions, keep device data in sync, and communicate with other devices securely – even when not connected to the Internet. Using AWS Lambda, Greengrass ensures your IoT devices can respond quickly to local events, use Lambda functions running on Greengrass Core to interact with local resources, operate with intermittent connections, stay updated with over the air updates, and minimize the cost of transmitting IoT data to the cloud.

| [__blog__](https://aws.amazon.com/greengrass/) |

<p align="center"><img src="images/amazon-greengrass-arch.png" width="90%"/></p>

### GraphPipe ([Oracle](https://www.oracle.com/index.html))

> GraphPipe is a protocol and collection of software designed to simplify machine learning model deployment and decouple it from framework-specific model implementations.

| [__homepage__](https://oracle.github.io/graphpipe/#/) | [__github__](https://github.com/oracle/graphpipe) | [__documentation__](https://oracle.github.io/graphpipe/#/guide/user-guide/overview) |

#### Architecture:

<p align="center"><img src="images/oracle-graphpipe-arch.jpg" width="70%"/></p>

#### Features:

- A minimalist machine learning transport specification based on [flatbuffers](https://google.github.io/flatbuffers/)

- Simple, efficient reference model servers for Tensorflow, Caffe2, and ONNX.

- Efficient client implementations in Go, Python, and Java.

### TensorFlow XLA (Accelerated Linear Algebra) ([Google](https://www.google.com/about/))

> **XLA** (Accelerated Linear Algebra) is a **domain-specific compiler** for linear algebra that optimizes TensorFlow computations. The results are improvements in speed, memory usage, and portability on server and mobile platforms.

> **Improve execution speed**. Compile subgraphs to reduce the execution time of short-lived Ops to eliminate overhead from the TensorFlow runtime, fuse pipelined operations to reduce memory overhead, and specialize to known tensor shapes to allow for more aggressive constant propagation.

> **Improve memory usage**. Analyze and schedule memory usage, in principle eliminating many intermediate storage buffers.

> **Reduce reliance on custom Ops**. Remove the need for many custom Ops by improving the performance of automatically fused low-level Ops to match the performance of custom Ops that were fused by hand.

> **Reduce mobile footprint**. Eliminate the TensorFlow runtime by ahead-of-time compiling the subgraph and emitting an object/header file pair that can be linked directly into another application. The results can reduce the footprint for mobile inference by several orders of magnitude.

> **Improve portability**. Make it relatively easy to write a new backend for novel hardware, at which point a large fraction of TensorFlow programs will run unmodified on that hardware. This is in contrast with the approach of specializing individual monolithic Ops for new hardware, which requires TensorFlow programs to be rewritten to make use of those Ops.

| [__homepage__](https://www.tensorflow.org/xla/) | [__github__](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/compiler) | [__documentation__](https://www.tensorflow.org/xla/overview) | [__blog__](https://developers.googleblog.com/2017/03/xla-tensorflow-compiled.html) | [__talk__](https://www.youtube.com/watch?time_continue=6&v=kAOanJczHA0) |

#### Compilation Process:

<p align="center"><img src="images/google-xla-arch.png" width="50%"/></p>

#### Components:

- TensorFlow graphs compiled
- Just-In-Time (JIT) compilation
- Ahead-Of-Time (AOT) compilation

### Swift for TensorFlow

> Swift for TensorFlow is a new way to develop machine learning models. It gives you the power of TensorFlow directly integrated into the [Swift programming language](https://swift.org/). With Swift, you can write the following imperative code, and Swift automatically turns it into **a single TensorFlow Graph** and runs it with the full performance of TensorFlow Sessions on CPU, GPU and TPU.

> Swift combines the flexibility of [Eager Execution](https://www.tensorflow.org/guide/eager) with the high performance of [Graphs and Sessions](https://www.tensorflow.org/guide/graphs). Behind the scenes, Swift analyzes your Tensor code and automatically builds graphs for you. Swift also catches type errors and shape mismatches before running your code, and has [Automatic Differentiation](https://en.wikipedia.org/wiki/Automatic_differentiation) built right in. We believe that machine learning tools are so important that they deserve a **first-class language and a compiler**.

| [__homepage__](https://www.tensorflow.org/swift/api_docs/) | [__github__](https://github.com/tensorflow/swift) | [__design overview__](https://github.com/tensorflow/swift/blob/master/docs/DesignOverview.md) | [__tech deep dive__](https://github.com/tensorflow/swift#technology-deep-dive) |

#### Compiler:

<p align="center"><img src="images/swift-compiler.png" width="90%"/></p>

Related project - DLVM (Modern Compiler Infrastructure for Deep Learning Systems):

| [__homepage__](http://dlvm.org/) | [__github__](https://github.com/dlvm-team) | [__paper1__](https://arxiv.org/abs/1711.03016) | [__paper2__](https://openreview.net/forum?id=SJo1PLzCW) | [__paper3__](http://learningsys.org/nips17/assets/papers/paper_23.pdf) |

### JAX - Autograd and XLA ([Google](https://www.google.com/about/))

> JAX is [Autograd](https://github.com/hips/autograd) and
[XLA](https://github.com/tensorflow/tensorflow/blob/master/tensorflow/compiler/xla/g3doc/overview.md),
brought together for high-performance machine learning research.
With its updated version of [Autograd](https://github.com/hips/autograd),
JAX can automatically differentiate native
Python and NumPy functions. It can differentiate through loops, branches,
recursion, and closures, and it can take derivatives of derivatives of
derivatives. It supports reverse-mode differentiation (a.k.a. backpropagation)
as well as forward-mode differentiation, and the two can be composed arbitrarily
to any order.

| [__github__](https://github.com/google/jax) |

### How It Works:

<p align="center"><img src="images/google-jax-arch.png" width="90%"/></p>

### PocketFlow ([Tencent](https://www.tencent.com/en-us/))

> PocketFlow is an open-source framework for compressing and accelerating deep learning models with minimal human effort. Deep learning is widely used in various areas, such as computer vision, speech recognition, and natural language translation. However, deep learning models are often computational expensive, which limits further applications on **mobile devices** with limited computational resources.

| [__homepage__](https://pocketflow.github.io/) | [__github__](https://github.com/Tencent/PocketFlow) |

<p align="center"><img src="images/tencent-pocketflow-arch.png" width="90%"/></p>

### TVM - End to End Deep Learning Compiler Stack ([Amazon](https://aws.amazon.com/?nc2=h_lg))

> TVM is a compiler stack for deep learning systems. It is designed to close the gap between the productivity-focused deep learning frameworks, and the performance- and efficiency-focused hardware backends. TVM works with deep learning frameworks to provide end to end compilation to different backends. Checkout the tvm stack homepage for more information.

| [__homepage__](https://tvm.ai/) | [__github__](https://github.com/dmlc/tvm) | [__documentation__](https://docs.tvm.ai/) | [__paper__](https://arxiv.org/abs/1802.04799) |

#### Architecture:

<p align="center"><img src="images/amazon-tvm-arch.png" width="90%"/></p>

#### Components:

- **Compilation of deep learning models** in Keras, MXNet, PyTorch, Tensorflow, CoreML, DarkNet into minimum deploy-able modules on diverse hardware backends.

- **Infrastructure to automatic generate and optimize tensor operators** on more backend with better performance.

### SageMaker Neo ([Amazon](https://aws.amazon.com/?nc2=h_lg))

> Amazon SageMaker Neo enables developers to train machine learning models once and run them anywhere in the cloud and at the edge. Amazon SageMaker Neo optimizes models to run up to twice as fast, with less than a tenth of the memory footprint, with no loss in accuracy.

| [__homepage__](https://aws.amazon.com/sagemaker/neo/) | [__github__](https://github.com/neo-ai/) | [__blog__](https://aws.amazon.com/blogs/aws/amazon-sagemaker-neo-train-your-machine-learning-models-once-run-them-anywhere/) |

<p align="center"><img src="images/amazon-sagemaker-neo-arch.png" width="90%"/></p>

### Tensor Comprehensions ([Facebook](https://www.facebook.com/))

> Tensor Comprehensions (TC) is a fully-functional C++ library to *automatically* synthesize high-performance machine learning kernels using [Halide](https://github.com/halide/Halide), [ISL](http://isl.gforge.inria.fr/) and NVRTC or LLVM. TC additionally provides basic integration with Caffe2 and PyTorch. We provide more details in our paper on [arXiv](https://arxiv.org/abs/1802.04730).

| [__homepage__](https://facebookresearch.github.io/TensorComprehensions/) | [__github__](https://github.com/facebookresearch/TensorComprehensions) | [__paper__](https://arxiv.org/abs/1802.04730) | [__blog__](https://research.fb.com/announcing-tensor-comprehensions/) |

#### Architecture:

<p align="center"><img src="images/facebook-tensor-comprehensions-arch.png" width="90%"/></p>

### Glow - A community-driven approach to AI infrastructure ([Facebook](https://www.facebook.com/))

> Glow is a machine learning compiler that accelerates the performance of deep learning frameworks on different hardware platforms. It enables the ecosystem of hardware developers and researchers to focus on building next gen hardware accelerators that can be supported by deep learning frameworks like PyTorch.

| [ __homepage__](https://facebook.ai/developers/tools/glow) | [__github__](https://github.com/pytorch/glow) |
[__paper__](https://arxiv.org/abs/1805.00907) | [__blog__](https://code.fb.com/ml-applications/glow-a-community-driven-approach-to-ai-infrastructure/) |

#### Architecture:

<p align="center"><img src="images/facebook-glow-arch.gif" width="90%"/></p>

#### Components:

- **High-level intermediate representation** allows the optimizer to perform domain-specific optimizations.

- **Lower-level intermediate representation**, an instruction-based address-only representation allows the compiler to perform memory-related optimizations, such as instruction scheduling, static memory allocation, and copy elimination.

- The **optimizer** then performs machine-specific code generation to take advantage of specialized hardware features.

### nGraph - A New Open Source Compiler for Deep Learning Systems ([Intel](https://ai.intel.com/))

> We are pleased to announce the open sourcing of nGraph, a framework-neutral Deep Neural Network (DNN) model compiler that can target a variety of devices. With nGraph, data scientists can focus on data science rather than worrying about how to adapt their DNN models to train and run efficiently on different devices.

| [__homepage__](https://ai.intel.com/intel-ngraph/) | [__documentation__](http://ngraph.nervanasys.com/index.html/) | [__github__](https://github.com/NervanaSystems/ngraph) | [__paper__](https://arxiv.org/abs/1801.08058) |

#### Architecture:

<p align="center"><img src="images/intel-ngraph-arch.png" width="90%"/></p>

#### Components:

- **Fusion**: Fuse multiple ops to to decrease memory usage.

- **Data layout abstraction**: Make abstraction easier and faster with nGraph translating element order to work best for a given or available device.

- **Data reuse**: Save results and reuse for subgraphs with the same input.

- **Graph scheduling**: Run similar subgraphs in parallel via multi-threading.

- **Graph partitioning**: Partition subgraphs to run on different devices to speed up computation; make better use of spare CPU cycles with nGraph.

- **Memory management**: Prevent peak memory usage by intercepting a graph with or by a "saved checkpoint," and to enable data auditing.

### ONNX - Open Neural Network Exchange

> ONNX is a open format to represent deep learning models. With ONNX, AI developers can more easily move models between state-of-the-art tools and choose the combination that is best for them. ONNX is developed and supported by a community of partners.

| [__homepage__](https://onnx.ai/) | [__documentation__](https://onnx.ai/getting-started) | [__github__](https://github.com/onnx) |

#### Architecture:

<p align="center"><img src="images/onnx-arch.png" width="90%"/></p>

#### Components:

- **Framework Interoperability**: enabling interoperability makes it possible to get great ideas into production faster. ONNX enables models to be trained in one framework and transferred to another for inference.

- **Hardware Optimizations**: ONNX makes it easier for optimizations to reach more developers. Any tools exporting ONNX models can benefit ONNX-compatible runtimes and libraries designed to maximize performance on some of the best hardware in the industry.

### MLIR - "Multi-Level Intermediate Representation" Compiler Infrastructure

> The MLIR project aims to define a common intermediate representation (IR) that will unify the infrastructure required to execute high performance machine learning models in TensorFlow and similar ML frameworks. This project will include the application of HPC techniques, along with integration of search algorithms like reinforcement learning. This project aims to reduce the cost to bring up new hardware, and improve usability for existing TensorFlow users.

| [__homepage__]() | [__github__](https://github.com/tensorflow/mlir) | [__talk__](https://www.youtube.com/watch?v=qzljG6DKgic) | [__slices__](https://llvm.org/devmtg/2019-04/slides/Keynote-ShpeismanLattner-MLIR.pdf) |

#### Architecture:

<p align="center"><img src="images/mlir-arch.png" width="90%"/></p>

#### Goal:

Global improvements to TensorFlow infrastructure, SSA-based designs to generalize and improve ML “graphs”:

- Better side effect modeling and control flow representation

- Improve generality of the lowering passes

- Dramatically increase code reuse

- Fix location tracking and other pervasive issues for better user experience 

###  Neural Network Distiller ([Intel](https://ai.intel.com/))

> Distiller is an open-source Python package for neural network compression research.
Network compression can reduce the footprint of a neural network, increase its inference speed and save energy. Distiller provides a PyTorch environment for prototyping and analyzing compression algorithms, such as sparsity-inducing methods and low precision arithmetic.

| [__homepage__](https://nervanasystems.github.io/distiller/index.html) | [__github__](https://github.com/NervanaSystems/distiller/) | [__documentation__](https://nervanasystems.github.io/distiller/usage/index.html) |

#### Workflow:

<p align="center"><img src="images/intel-distiller-arch.png" width="70%"/></p>

#### Components:

- A framework for integrating pruning, regularization and quantization algorithms.

- A set of tools for analyzing and evaluating compression performance.

- Example implementations of state-of-the-art compression algorithms.

### MACE - Mobile AI Compute Engine ([XiaoMi](https://www.mi.com/global/))

> MACE (Mobile AI Compute Engine) is a deep learning inference framework optimized for mobile heterogeneous computing platforms. MACE provides tools and documents to help users to deploy deep learning models to mobile phones, tablets, personal computers and IoT devices.

| [__github__](https://github.com/XiaoMi/mace) | [__documentation__](https://mace.readthedocs.io/en/latest/introduction.html) |

#### Architecture:

<p align="center"><img src="images/xiaomi-mace-arch.png" width="50%"/></p>

### Components:

* Performance
  * Runtime is optimized with NEON, OpenCL and Hexagon, and
    [Winograd algorithm](https://arxiv.org/abs/1509.09308) is introduced to
    speed up convolution operations. The initialization is also optimized to be faster.
* Power consumption
  * Chip dependent power options like big.LITTLE scheduling, Adreno GPU hints are
    included as advanced APIs.
* Responsiveness
  * UI responsiveness guarantee is sometimes obligatory when running a model.
    Mechanism like automatically breaking OpenCL kernel into small units is
    introduced to allow better preemption for the UI rendering task.
* Memory usage and library footprint
  * Graph level memory allocation optimization and buffer reuse are supported.
    The core library tries to keep minimum external dependencies to keep the
    library footprint small.
* Model protection
  * Model protection has been the highest priority since the beginning of
    the design. Various techniques are introduced like converting models to C++
    code and literal obfuscations.
* Platform coverage
  * Good coverage of recent Qualcomm, MediaTek, Pinecone and other ARM based
    chips. CPU runtime is also compatible with most POSIX systems and
    architectures with limited performance.
* Rich model formats support
  * [TensorFlow](https://github.com/tensorflow/tensorflow),
    [Caffe](https://github.com/BVLC/caffe) and
    [ONNX](https://github.com/onnx/onnx) model formats are supported.

### AMC - AutoML for Model Compression engine

> We propose AutoML for Model Compression (AMC) which leverage [reinforcement learning](https://en.wikipedia.org/wiki/Reinforcement_learning) to provide the model compression policy. This learning-based compression policy outperforms conventional rule-based compression policy by having higher compression ratio, better preserving the accuracy and freeing human labor.

| [__paper__](https://arxiv.org/abs/1802.03494) |

#### Architecture:

<p align="center"><img src="images/amc-arch.png" width="90%"/></p>

#### Insight:

- **Automated Compression with Reinforcement Learning**, AMC leverages reinforcement learning for efficient search over action space.

- **Search Protocols**: resource-constrained compression,
accuracy-guaranteed compression.

# Courses

#### CSE 599W Systems for ML (University of Washington)

> This course will be covering various aspects of deep learning systems, including: basics of deep learning, programming models for expressing machine learning models, automatic differentiation, memory optimization, scheduling, distributed learning, hardware acceleration, domain specific languages, and model serving. Many of these topics intersect with existing research directions in databases, systems and networking, architecture and programming languages. The goal is to offer a comprehensive picture on how deep learning systems works, discuss and execute on possible research opportunities, and build open-source software that will have broad appeal.

| [__link__](http://dlsys.cs.washington.edu/) | [__github__](https://github.com/dlsys-course/dlsys-course.github.io) | [__materials__](http://dlsys.cs.washington.edu/schedule) |

#### CSCE 790: Machine Learning Systems

> In this course, we will learn the fundamental differences between ML as a technique versus ML as a system in production. A machine learning system involves a significant number of components and it is important that they remain responsive in the face of failure and changes in load. This course covers several strategies to keep ML systems responsive, resilient, and elastic. Machine learning systems are different than other computer systems when it comes to building, testing, deploying, delivering, and evolving. ML systems also have unique challenges when we need to change the architecture or behavior of the system. Therefore, it is essential to learn how to deal with such unique challenges that only may happen when building real-world production-ready ML systems (e.g., performance issues, memory leaking, communication issues, multi-GPU issues, etc). The focus of this course will be primarily on deep learning systems, but the principles will remain similar across all ML systems.

| [__link__](https://pooyanjamshidi.github.io/mls/) | [__github__](https://github.com/pooyanjamshidi/mls) | [__materials__](https://pooyanjamshidi.github.io/mls/lectures/) |

# Conferences

#### [SysML - Conference on Systems and Machine Learning @ Stanford](https://www.sysml.cc/)

#### [ML Systems Workshop @ NeurIPS](http://learningsys.org)

#### [ScaledML - Scaling ML models, data, algorithms & infrastructure](http://scaledml.org/)

# Papers

## Survey / Reviews

#### [A Survey on Compiler Autotuning using Machine Learning](https://arxiv.org/abs/1801.04405)

> This survey summarizes and classifies the recent advances in using machine learning for the compiler optimization field, particularly on the two major problems of (1) selecting the best optimizations and (2) the phase-ordering of optimizations. The survey highlights the approaches taken so far, the obtained results, the fine-grain classification among different approaches and finally, the influential papers of the field.

#### [A Survey of Model Compression and Acceleration for Deep Neural Networks](https://arxiv.org/abs/1710.09282)

> In this paper, we survey the recent advanced techniques for compacting and accelerating CNNs model developed. These techniques are roughly categorized into four schemes: parameter pruning and sharing, low-rank factorization, transfered/compact convolutional filters and knowledge distillation. Methods of parameter pruning and sharing will be described at the beginning, after that the other techniques will be introduced. For each scheme, we provide insightful analysis regarding the performance, related applications, advantages and drawbacks etc. Then we will go through a few very recent additional successful methods, for example, dynamic networks and stochastic depths networks. After that, we survey the evaluation matrix, main datasets used for evaluating the model performance and recent bench-marking efforts. Finally we conclude this paper, discuss remaining challenges and possible directions in this topic.

## Large-Scale / Distributed Learning

### Milestones

Major milestones for "[ImageNet](http://www.image-net.org/) in X nanoseconds" :roller_coaster:.

| initial date | resources             | elapsed           | top-1 accuracy | batch size | link                             |
|--------------|-----------------------|-------------------|----------------|------------|----------------------------------|
| June 2017    | 256 NVIDIA P100 GPUs  | 1 hour            | 76.3%          | 8192       | https://arxiv.org/abs/1706.02677 |
| Aug 2017     | 256 NVIDIA P100 GPUs  | 50 mins           | 75.01%         | 8192       | https://arxiv.org/abs/1708.02188 |
| Sep 2017     | 512 KNLs -> 2048 KNLs | 1 hour -> 20 mins | 72.4% -> 75.4% | 32768      | https://arxiv.org/abs/1709.05011 |
| Nov 2017     | 128 Google TPUs (v2)  | 30 mins           | 76.1%          | 16384      | https://arxiv.org/abs/1711.00489 |
| Nov 2017     | 1024 NVIDIA P100 GPUs | 15 mins           | 74.9%          | 32768      | https://arxiv.org/abs/1711.04325 |
| Jul 2018     | 2048 NVIDIA P40 GPUs  | 6.6 mins          | 75.8%          | 65536      | https://arxiv.org/abs/1807.11205 |
| Nov 2018     | 2176 NVIDIA V100 GPUs | 3.7 mins          | 75.03%         | 69632      | https://arxiv.org/abs/1811.06992 |
| Nov 2018     | 1024 Google TPUs (v3) | 2.2 mins          | 76.3%          | 32768      | https://arxiv.org/abs/1811.06992 |

#### [Accurate, Large Minibatch SGD: Training ImageNet in 1 Hour](https://arxiv.org/abs/1706.02677)

- Learning rate linear scaling rule
- Learning rate warmup (constant, gradual)
- Communication: [recursive halving and doubling algorithm](https://pdfs.semanticscholar.org/8d44/e92b3597d9e3f5245e152c9e0ce55b3e68a4.pdf)

#### [PowerAI DDL](https://arxiv.org/abs/1708.02188)

- Topology-aware communication

#### [ImageNet Training in Minutes](https://arxiv.org/abs/1709.05011)

-  Layer-wise Adaptive Rate Scaling (LARS)

#### [Don't Decay the Learning Rate, Increase the Batch Size](https://arxiv.org/abs/1711.00489)

- Decaying the learning rate is simulated annealing
- Instead of decaying the learning rate, increase the
batch size during training

#### [Extremely Large Minibatch SGD: Training ResNet-50 on ImageNet in 15 Minutes](https://arxiv.org/abs/1711.04325)

- RMSprop Warm-up
- Slow-start learning rate schedule
- Batch normalization without moving averages

#### [Highly Scalable Deep Learning Training System with Mixed-Precision: Training ImageNet in Four Minutes](https://arxiv.org/abs/1807.11205)

- Mixed precision
- Layer-wise Adaptive Rate Scaling (LARS)
- Improvements on model architecture
- Communication: tensor fusion, hierarchical all-reduce, hybrid all-reduce

#### [ImageNet/ResNet-50 Training in 224 Seconds](https://arxiv.org/abs/1811.05233)

- Batch size control to reduce accuracy degradation with mini-batch size exceeding 32K
- Communication: 2D-torus all-reduce

#### [Image Classification at Supercomputer Scale](https://arxiv.org/abs/1811.06992)

- Mixed precision
- Layer-wise Adaptive Rate Scaling (LARS)
- Distributed batch normalization
- Input pipeline optimization: dataset sharding and caching, prefetch, fused JPEG decoding and cropping, parallel data parsing
- Communication: 2D gradient summation

## Federated Learning

#### [Communication-Efficient Learning of Deep Networks from Decentralized Data](https://arxiv.org/abs/1602.05629)

#### [Federated Learning: Strategies for Improving Communication Efficiency](https://arxiv.org/abs/1610.05492)

#### [Practical Secure Aggregation for Privacy-Preserving Machine Learning](https://eprint.iacr.org/2017/281.pdf)

#### [Federated Multi-Task Learning](https://arxiv.org/abs/1705.10467)

#### [Protection Against Reconstruction and Its Applications in Private Federated Learning](https://arxiv.org/abs/1812.00984)

#### [Differentially Private Distributed Learning for Language Modeling Tasks](https://arxiv.org/abs/1712.07473)

#### [Differentially Private Federated Learning: A Client Level Perspective](https://arxiv.org/abs/1712.07557)

#### [Federated Learning for Mobile Keyboard Prediction](https://arxiv.org/abs/1811.03604)

#### [A Generic Framework for Privacy Preserving Deep Learning](https://arxiv.org/abs/1811.04017)
