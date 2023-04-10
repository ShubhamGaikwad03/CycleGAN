# Abstract

CAPTION TO IMAGE. 
 * A research project aimed at generating images from captions using state-of-the-art GAN (Generative Adversarial Network) architecture. 
 * The researchers used Attention-based GANs as a baseline model and improved upon it by creating a novel cyclic design that can learn an inverse function to map the image back to the original caption. 


# 4. Method

The researchers preprocessed the data by cropping and downsampling the images, and splitting the data into train and test sets. They used two different models - AttnGAN and CycleGAN - to generate images from the captions. AttnGAN used attention and Conditioning Augmentation to generate images in different resolutions, while CycleGAN used an RNN and a Semantic Text Regeneration and Alignment Module (STREAM) to convert the generated images back to the original captions. 


CycleGAN has a generator and discriminator. 
