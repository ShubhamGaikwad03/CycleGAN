# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks

CONVERT IMAGES FROM ONE TYPE TO ANOTHER. 

In this paper, we present a system that can learn to do the same: capturing special characteristics of one image collection
and figuring out how these characteristics could be translated into the other image collection, all in the absence of any paired
training example

The passage you provided is discussing a problem in computer vision called "image-to-image translation." This refers to the process of converting an image from one representation of a scene to another, such as from grayscale to color or from an edge-map to a photograph.

Traditionally, this process has been done in a supervised setting, where a computer program is trained using pairs of example images that show both the input image and the desired output image. However, obtaining these pairs of images can be difficult and expensive, especially for complex tasks like artistic stylization or object transfiguration.

The authors propose an alternative approach to this problem that **doesn't require paired training data**. Instead, they seek to learn a mapping between the two domains of images (e.g., grayscale and color) without any supervision at the level of individual pairs. They do this by training a mapping function G that converts images from domain X to domain Y, and an inverse mapping function F that converts images from domain Y back to domain X. By **training both of these functions simultaneously and adding a "cycle consistency loss" that encourages the output of G and F to be similar to the original input images**, they can learn to translate between the two domains without any paired examples.


G(X) - Y
F(Y) - X

Also,
F(G(x)) ≈ x 
G(F(y)) ≈ y

In the authors' work, they introduce a similar cycle consistency loss to ensure consistency between the mapping functions G and F.

The adversarial losses help the program generate images that look more realistic, while the cycle consistency loss ensures that the mappings between the two domains are consistent with each other.

In summary, the goal of this program is to generate high-quality images that look like they belong in a specific domain by learning mappings between two domains and using adversarial losses and cycle consistency loss to ensure that the generated images are of high quality and consistent with each other.

## 3. Formulation


DX and DY, which distinguish between translated images and real images.
the image translation cycle should be able to bring x back to the original image, i.e. x → G(x) → F(G(x)) ≈ x. We call this forward cycle consistency. Similarly, as illustrated in Figure 3
(c), for each image y from domain Y , G and F should also satisfy
backward cycle consistency: y → F(y) → G(F(y)) ≈ y.


Our objective contains kinds of two terms: 
adversarial losses [14] for matching the distribution of generated images to the data distribution in the target domain; 
and a cycle consistency loss to prevent the learned mappings G and F from contradicting each other

**Neural style transfer** is a technique that involves generating an image by combining the style of one image with the content of another image. This technique is achieved by using a pre-trained convolutional neural network (CNN) to extract the content and style features of the input images. These features are then used to generate an output image that preserves the content of the original image while incorporating the style of the other image. Neural style transfer has various applications in fields such as art, design, and photography.

**Super-resolution**, on the other hand, is a technique that involves generating a high-resolution image from a low-resolution input image. This task is achieved by using deep learning models that can learn the mapping between low-resolution and high-resolution images. Super-resolution has various applications in fields such as medical imaging, surveillance, and image editing.

Discriminator network is a part of a computer program that is designed to tell whether a picture is "real" (i.e., it was taken by a camera or drawn by a human) or "fake.

Generating a GAN generator involves training a neural network to create new data samples that are similar to a given dataset by using a feedback loop with a discriminator that tries to distinguish between the generated data and the real data. 

GAN generators are used for generating new data samples that are similar to a given dataset and can be used for a wide range of applications, including data augmentation, image and video synthesis, style transfer, anomaly detection, and data privacy.

### Comparison against baseline

This section compares the proposed method, CycleGAN, against different baselines for image-to-image translation. The baselines include CoGAN, Pixel loss + GAN, and Feature loss + GAN. The authors show that the baselines fail to produce compelling results, while CycleGAN is able to produce translations that are often of similar quality to the fully supervised pix2pix.

### Applications

The proposed method, CycleGAN, is demonstrated on several applications where paired training data does not exist.
* Object transfiguration: The model is trained to translate one object class from Imagenet to another. This application focuses on object transfiguration between visually similar categories, as opposed to within the same category as proposed by Turmukhambetov et al.
* Season transfer: The model is trained on winter and summer photos of Yosemite on Flickr.
Collection style transfer: The model is trained on landscape photographs downloaded from Flickr and WikiArt, and learns to mimic the style of an entire set of artworks rather than a single piece of art as in neural style transfer.
* Photo generation from paintings: An additional loss is introduced to encourage the mapping to preserve color composition between the input and output. This identity mapping loss helps to prevent the generator from changing the tint of input images unnecessarily.
* Photo enhancement: The model is trained on flower photos downloaded from Flickr to generate photos with shallower depth of field from photos taken by smartphones, which usually have a deep depth of field due to a small aperture.