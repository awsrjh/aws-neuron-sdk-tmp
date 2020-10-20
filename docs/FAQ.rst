AWS Neuron: Frequently Asked Questions
======================================

Getting started with Neuron FAQs
--------------------------------

Q: How can I get started?
~~~~~~~~~~~~~~~~~~~~~~~~~

You can start your workflow by training your model in one of the popular
ML frameworks using EC2 GPU instances such as P3 or P3dn, or
alternativelly download a pre-training model. Once the model is trained
to your required accuracy, you can use the ML frameworks' API to invoke
Neuron, the software development kit for Inferentia, to
re-target(compile) the model for execution on Inferentia. This latter
step is done once and the developer doesnt need to redo it as long as
the model is not changing. Once compiled, the Inferentia binary can be
loaded into one or more Inferentia, and can service inference calls. In
order to get started quickly, you can use `AWS Deep Learning
AMIs <https://aws.amazon.com/machine-learning/amis/>`__ that come
pre-installed with ML frameworks and the Neuron SDK. For a fully managed
experience, you will soon be able to use Amazon SageMaker which will
enable you to seamlessly deploy your trained models on Inf1 instances.

For customers who use popular frameworks like TensorFlow, MXNet and
PyTorch, a guide to help you get started with frameworks is available
at:

-  :ref:`neuron-tensorflow`
-  :ref:`neuron-pytorch`
-  :ref:`neuron-mxnet`

You can also visit :ref:`neuron-gettingstarted`.

Q: How do I select which Inf1 instance to use?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The decision as to which Inf1 instance size to use is based upon the
application and the performance/cost targets and may differ for each
workload. To assist, the Neuron compiler provides guidance on expected
performance for various Inf1 instance sizes, and TensorBoard profiling
will show actual results when executed on a given instance. A guide to
this process is available here: :ref:`tensorboard-neuron`.

Ultimately, AWS encourages developers try out all the Inf1 instance
sizes (which can be done at low cost and quickly in the cloud
environment), with their specific models, and choose the right instance
for them.

General Neuron FAQs
-------------------

Q: What ML models types and operators are supported by AWS Neuron?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

AWS Neuron includes a compiler that converts your trained machine
learning model to Inferentia binary object for execution. The Neuron
compiler supports many commonly used machine learning models such as
ResNet for image recognition, and Transformer and BERT for natural
language processing and translation. A list of supported ML operators
and supported inputs are in :ref:`neuron-supported-operators` .

AWS continues to grow these lists based on customers' feedback.

Q: Why is a compiler needed, and how do I use it?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Neuron compiler converts from a framework level Neural Network
graph, with operators like convolution and pooling, into the
hardware-specific instruction set of Inferentia, build the schedule for
execution these instructions, and convers the model parameters into
format that Inferentia can consume. The supported input formats include
TensorFlow, PyTorch (shortly), MXNet, or ONNX. The output from the
compiler is a Neuron Executable File Format (NEFF) artifact. NEFF
contains a combination of binary code, the model parameters, and
additional meta-data needed by the runtime and profiler.

Q: I am using a ML framework today – what will change for me to use this?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The likely (but not only) workflow for developers is a hand-off of
pre-trained model to large scale of inference fleet. To use Inferentia
and Inf1 instances, the developer need to perform one-time compilation
of the pre-trained model to generate NEFF, and use this as the inference
model in fleet of Inf1 instances.

-  :ref:`neuron-tensorflow`
-  :ref:`neuron-pytorch`
-  :ref:`neuron-mxnet`

Q: What is a NeuronCore Pipeline ? and How do I take advantage of it?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A NeuronCore Pipeline is a unique technique to shard a specific Neural
Network across multiple NeuronCores, to take advantage of the large
on-chip cache that will typically increase throughput and reduce latency
at low batch sizes. All Inf1 instances support it, and the Inf1
instances with multiple Inferentia accelerators, such as inf1.6xlarge or
inf1.24xlarge support it thanks to the fast chip-to-chip interconnect.

Developers can choose to use NeuronCore Pipeline mode during compile
stage, with an opt-in flag. :ref:`neuron-cc` provides further details.

Q: NeuronCores, NeuronCore Groups and NeuronCore Pipelines: What do they do?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Each Inferentia chip has four compute engines called NeuronCores. A
NeuronCore Group is a way to aggregate NeuronCores to improve hardware
utilization and assign models with the right compute sizing for a
specific application. If you want to run mutliple models in parallel,
you can assign different models to separate NeuronCore Groups. A model
compiled to use multiple NeuronCores in a NeuronCorePipeline can be
assigned to a NeuronCore Group with enough NeuronCores to load it.
Finally- it is also possible for sets of Inferentia devices to be mapped
to separate Neuron Runtimes. :ref:`neuron-fundamentals` section has more
information and examples.

Q: Can I use TensorFlow networks from tfhub.dev as-is ? if not, what should I do?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Yes. Models format can be imported into TensorFlow, either as a standard
model-server, in which case it appears as a simple command line utility,
or via the Python based TensorFlow environment. The primary additional
step needed is to compile the model into Inferentia NEFF format.

Troubleshooting FAQs
--------------------

Q: Performance is not what I expect it to be, what's the next step?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Please check our :ref:`performance-optimization` section on performance
tuning and other notes on how to use pipelining and batching to improve
performance!

Q: Do I need to worry about size of model and size of inferentia memory? what problems can I expect to have?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Errors like this wil be logged and can be found as shown
:ref:`neuron_gatherinfo`.

Q: How can I debug / profile my inference request?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

See :ref:`tensorboard-neuron`
