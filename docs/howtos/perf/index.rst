.. _performance-optimization:

Performance Optimization
------------------------

Neuron provides developers with various performance optimization options. Two of the most widely used ones are Batching and NeuronCore-Pipeline. Both techniques aim to keep the data close to the compute engines to improve hardware utilization, but achieve that in different ways. In batching it is achieved by loading the data into an on-chip cache and reusing it multiple times for multiple different model-inputs, while in pipelining this is achieved by caching all model parameters into the on-chip cache across multiple NeuronCores and streaming the calculation across them. For more details on the NeuronCore Pipeline checkout the tech note `here <./docs/technotes/neuroncore-pipeline.md>`__, and for more details on Neuron Batching, please read the tech note `here <./docs/technotes/neuroncore-batching.md>`__.

Another capability, called NeuronCore Groups allows developers to assign different models to separate NeuronCores, and run the same or multiple models in parallel. NeuronCore Groups may be useful for increasing accuracy through majority-vote, or when different models need to run as a pipeline. For more details please read more `here <./docs/tensorflow-neuron/tutorial-NeuronCore-Group.md>`__.

.. toctree::
   :maxdepth: 1

   performance-tuning
