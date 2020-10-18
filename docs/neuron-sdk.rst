.. _neuron-sdk:

Neuron SDK Overview
====================

AWS Neuron is a software development kit (SDK) enabling high-performance deep learning inference using AWS Inferentia custom designed machine learning chips. With Neuron, you can develop, profile, and deploy high-performance inference predictions on top of Inferentia based `EC2 Inf1 instances <https://aws.amazon.com/ec2/instance-types/inf1/>`__ .

Neuron is pre-integrated into popular machine learning frameworks like TensorFlow, MXNet and Pytorch to provide a seamless training-to-inference workflow. It includes a compiler, runtime driver, as well as debug and profiling utilities with a TensorBoard plugin for visualization.

Neuron developer flow
---------------------

Since Neuron is pre-integrated with popular frameworks, it can be easily incorporated into ML applications to provide high-performance inference predictions. Neuron is built to enable the above steps to be done from within an ML framework with the addition of the compilation step and load the model to the Inferentia chips. Neuron allows customers to keep training in 32-bit floating point for best accuracy and auto-convert the 32-bit trained model to run at speed of 16-bit using bfloat16 model.

.. image:: images/devflow.png

Once a model is trained to the required accuracy, it is compiled to an optimized binary form, referred to as a Neuron Executable File Format (NEFF), which is in turn loaded by the Neuron runtime driver to execute inference input requests on the Inferentia chips. The compilation step may be performed on any EC2 instance or on-premises.

Support
-------

If none of the github and online resources have an answer to your question, checkout the AWS Neuron `support forum <https://forums.aws.amazon.com/forum.jspa?forumID=355>`__.
