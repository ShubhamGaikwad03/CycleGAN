## Symbolic Music Genre Transfer with CycleGAN

CONVERT MUSIC FROM ONE GENRE TO ANOTHER

Generative models can be used for a variety of tasks, such as generating images, music, or text, and can be trained using various techniques such as Variational Autoencoders (VAEs) and Generative Adversarial Networks (GANs). These models can be used to create new data that is similar to the original data, or to transform data from one domain to another, such as changing the style or genre of music or images.


The author uses Deep generative models like GAN(generative adversarial networks), Variational Autoencoders(VAEs) for symbolic music genre transfer. To increase generator probability of producing more real data we use discriminators.    

**First application of GANs to symbolic music domain transfer**

GENERATOR  | DISCRIMINATOR

In the context of Generative Adversarial Networks (GANs), a discriminator is a neural network that is trained to distinguish between real data and generated data. The discriminator is part of a GAN system, which also includes a generator network that is trained to generate data that can fool the discriminator into thinking it is real.

During training, the generator creates fake data and the discriminator tries to distinguish between real and fake data. The generator is then adjusted based on the feedback it receives from the discriminator, so that it can create better fake data that can fool the discriminator.

The discriminator is typically a convolutional neural network (CNN) or a feedforward neural network that takes in data and produces a probability score between 0 and 1, indicating the likelihood that the input data is real. The discriminator's goal is to maximize its accuracy in distinguishing between real and fake data, while the generator's goal is to create fake data that can fool the discriminator.

In summary, the discriminator plays a crucial role in the GAN system by providing feedback to the generator, allowing it to improve over time and generate more realistic data.


## Future Work


Furthermore, the resulting music
has complex structure and generally sounds harmonic. In the
future we plan to develop more objective genre transfer metrics,
and further investigate the generalization capabilities and
robustness of the genre classifier metric. Incorporating richer
features such as velocities, note durations and instrumentation
could further improve the results and make genre transfers
more convincing and realistic. While in this paper we mainly
focused on evaluating the basic CycleGAN architecture, more
sophisticated architectures should be explored as well