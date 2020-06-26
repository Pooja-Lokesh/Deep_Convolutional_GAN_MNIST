# DCGAN : Deep Convolutional Generative Adversarial Networks


## Purpose of GANs :
- In autoencoders, we are needed to give the loss function to the network, in order to get the network learn , so that it can generate sample with the similar distribution of the input. 
- But we want the network to learn more smartly , we want it to construct it's own loss function in order to learn the distribution of the input samples and generate more accurate samples.
- This is why we need GANs. GANs have a discriminator which tells how accurate the generated sample is , and give the generator a feedback (gradient) to help it correct it's distribution and generate more accurate samples which are more close to the input's distribution.

## Steps followed :
    - it has three segments : encoder, generator, discriminator 
    - the encoder generates the latent space 
    - the latent space is passed onto the generator 
    - the generator generates samples taking in the distribution (mean, covariance) recorded in the latent space 
    - the discriminator has inputs given from two sides randomly, one is from the generator model, and the other is from the real samples 
    - the discrimintor , discriminates between the real and fake samples, to tell how close the fake one is to the real one 
    - this way it generates gradient and passes it to the generator in order to corrcet itself 
    - with more steps , the generator learns with the grdaients passed by the discriminator , and generates samples who's distribution is close to the real distribution 
    - in this way the generator generates fake samples which are so similar to the real ones that it fools the discriminator 
    - discriminator (D) is a learnable loss function for generator (G)
    
### Weak discriminator : 
Doesn't generate good gradients (thinks the generator is always right)

### Weak generator : 
Which thinks the discriminator is always right and keeps correcting the model even after reaching the best possible distribution 
