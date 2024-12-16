---
title: conditional sampling
date: 2024-11-18 14:01:38
tags: 扩散
---

## Unconditional sampling

#### Add noise

$$
P(x_0) \xrightarrow{\epsilon_1} P(x_1) \xrightarrow{\epsilon_2}  P(x_2) \xrightarrow{\epsilon_3} \cdots \xrightarrow{\epsilon_T} P(x_T) \approx \mathcal{N}(0, I)
$$

$$
x_t = a_t x_{t-1} + b_t \epsilon_t
$$

#### Denoise

$$
P(x_0) \xleftarrow{\epsilon_{\theta}(x_1,t)} P(x_1) \xleftarrow{\epsilon_{\theta}(x_2,t)} P(x_2) \xleftarrow{\epsilon_{\theta}(x_3,t)} \cdots \xleftarrow{\epsilon_{\theta}(x_T,t)} P(x_T) \approx \mathcal{N}(0, I)
$$

$$
x_{t-1} = \frac{x_t - b_t\epsilon_{\theta}(x_t,t)}{a_t}
$$

## conditional sampling

#### Add noise(same as unconditional)

$$
P(x_0) \xrightarrow{\epsilon_1} P(x_1) \xrightarrow{\epsilon_2}  P(x_2) \xrightarrow{\epsilon_3} \cdots \xrightarrow{\epsilon_T} P(x_T) \approx \mathcal{N}(0, I)
$$

$$
x_t = a_t x_{t-1} + b_t \epsilon_t
$$

#### Denoise

c represents the condition

$$
P(x_0) \xleftarrow{\epsilon_{\theta}(x_1,t,c)} P(x_1) \xleftarrow{\epsilon_{\theta}(x_2,t,c)} P(x_2) \xleftarrow{\epsilon_{\theta}(x_3,t,c)} \cdots \xleftarrow{\epsilon_{\theta}(x_T,t,c)} P(x_T) \approx \mathcal{N}(0, I)
$$

$$
x_{t-1} = \frac{x_t - b_t\epsilon_{\theta}(x_t,t,c)}{a_t}
$$

## Latent Space Diffusion + VAE

#### Train

- Get a image-text pair from the dataset
- Sampling a time step t, and a gaussian noise
- Use (pre-trained)VAE to encode the image to the latent space
- Use (pre-trained)CLIP to encode the text to the latent space
- Add noise to the latent space image
- Denoise the latent space image with text as input of epsilon model
- Backward

#### Sampling

- Sampling a gaussian-noise-image in the latent space
- Denoise the latent space gaussian-noise-image with text as input of epsilon model
- Decode the latent space image to the image space
