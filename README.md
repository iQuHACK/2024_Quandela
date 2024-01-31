# 2024_Quandela
Quandela iQuHACK 2024 In-Person Challenge


## Quantum generative adversarial learning in photonics

The goal of this challenge is to reproduce the results of [this paper](https://arxiv.org/abs/2310.00585). 

In the article, the authors implement a quantum adversarial generative model on a photonic circuit. The generator and the discriminator are directly connected to each other on the same chip: the generator's task is to prepare quantum states and the discriminator task is to be able to tell whether the state generated is the target state or not.

Generative adversarial networks (GANs) are a type of generative machine learning model. These attempt to learn the underlying distribution of the data in order to generate new samples. GANs are trained in an adversarial way against a discriminator (classifier). The discriminator alternatively receives real samples from the data and samples produced by the generator, and must classify them as real or fake. Consequently, as the discriminator becomes more performant, the generator must produce samples that are more and more convincing. More details on GANs can be found [here](https://developers.google.com/machine-learning/gan).

There are different ways of designing quantum versions of GANs, as proposed in [this paper](https://arxiv.org/abs/1804.09139) from 2018.

In this challenge, you will focus on the scenario where the generator and discriminator are both [quantum variational circuits](https://arxiv.org/abs/2012.09265), and the data consists of quantum states. 

Objectives:
Your aim is to generate the following rotation of the maximal entangled ququart state using a QGAN: $\frac{1}{2}(\ket{01} + \ket{12} +\ket{23} + \ket{30})$ 
1. Start by reproducing the circuit from Figure 1.d of the Wang et al. paper using Perceval.
2. Figure S1 contains the full circuit including the generation of the initial entangled states. You will notice that the authors generate these states using spontaneous four-wave mixing photon-pair sources. Can you do the same in a way that corresponds to Quandela's hardware? If not, what alternatives can you come up with? Here are some hints of possible approaches (all valid) you could follow:
 - have a look at [this paper](https://arxiv.org/abs/2302.07357),
 - use StateVector,
 - modify the scenario to work with (multipartite) qubit states and see if you obtain different results.
 - Bonus: can you build a separate QGAN to generate the initial state? (see below for more details)
4. Once the circuit is ready, train the QGAN using a variational approach. You will notice that several technical details are omitted in the article, so you will have to explore various options and see what works. This applies to the gradient evaluation, the optimizer, hyperparameters etc.
5. Bonus: can you add a noise model in Perceval? How does it affect your results?
6. Bonus: can you run this model directly on the Ascella QPU? If not, what adjustments would you need to make? If you have time, complete the challenge by running at least 1 evaluation of the model on Ascella.

Bonus QGAN to generate maximal entangled ququart state from single photons:

################ need to provide more details ################

---
Your mentors for this challenge will be Pierre-Emmanuel Emeriau and Samuel Horsch (on site) and Alexia Salavrakos (on Slack).

Please commit your code in the repository so we can keep track of your contribution. This will be part of the evaluation afterwards.

Good luck!