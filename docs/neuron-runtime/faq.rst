FAQs
----

**Q: How does Neuron connect to all the Inferentia chips in an Inf1
instance?**

By default, a single runtime process will manage all assigned
Inferentias, including running the Neuron Core Pipeline mode. if needed,
you can configure multiple KRT processes each managing a separate group
of Inferentia chips. For more details please refer to `Neuron Runtime
readme <./docs/neuron-runtime/README.md>`__

**Q: Where can I get logging and other telemetry information?** See this
document on how to collect logs: `Neuron log
collector <./docs/neuron-tools/tutorial-neuron-gatherinfo.md>`__

**Q: What about RedHat or other versions of Linux?** We dont officially
support it yet.

**Q: What about Windows?**

Windows is not supported at this time.

**Q: How can I use Neuron in a container based environment? Does Neuron
work with ECS and EKS?** ECS and EKS support is coming soon. Containers
can be configured as shown
`here <./docs/neuron-container-tools/README.md>`__

**Q: How can I take advantage of multiple NeuronCores to run multiple
inferences in parallel?** Examples of this for TensorFlow are found
`here <./docs/tensorflow-neuron/tutorial-NeuronCore-Group.md>`__ as well
as for MXNet
`here <./docs/mxnet-neuron/tutorial-neuroncore-groups.md>`__

