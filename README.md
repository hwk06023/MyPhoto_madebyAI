# MyPhoto_madebyAI

This repo is for an AI service project that provides ID photos and profile photos. The service is based on the Stable Diffusion model and the Dreambooth model. The Stable Diffusion model is a generative model that can generate high-quality images. The Dreambooth model is a fine-tuned version of the Stable Diffusion model that can generate images with a specific style. <br/>

I plan to serve this through an app or website to create a revenue structure. If you're interested in collaborating, please contact me at hwk06023@gmail.com. <br/>

### Outline

1. [Fine-tuning the RealisticVision model of Stable Diffusion with Dreambooth](##Fine-tuning-the-RealisticVision-model-of-Stable-Diffusion-with-Dreambooth)

2. [Effective service pipeline through a generic model](##Effective-service-pipeline-through-a-generic-model)



## Fine-tuning the RealisticVision model of Stable Diffusion with Dreambooth

#### Architectrue example
<img src="img/Architecture.png" width=500>

### Hyperparameters

#### Prior_loss_weight(loss func’s lambda value)
A constant value is multiplied by the class loss, serving as regularization to prevent overfitting to the instance. However, due to the issue of becoming less similar to the instance (underfitting), I gradually reduced the value from the 1.0 suggested in the paper and tested it.

#### Learning rate, Training steps
By appropriately adjusting these two values, I was get the better result about underfitting and overfitting.

### Application

#### Recontextualization (Text prompt)
The sentences were generated in the format specified by the authors, **"a [V] [class noun] [context description]."** Furthermore, for the V (Instance noun) to fit better, the name part was composed of less commonly used words by applying a Caesar cipher.

### LoRA (Low Rank Adaptation)

<img src = "img/lora.png" width=400>