# Text-to-Image Generation using Diffusion Models

## Overview
This project implements a Text-to-Image generation pipeline utilizing diffusion models, VAE (Variational AutoEncoder), and CLIP (Contrastive Language–Image Pretraining). It allows users to generate high-fidelity images from textual descriptions or edit input images using a noise-based approach.

The project leverages Classifier-Free Guidance (CFG) for improved output quality and includes support for text conditioning with CLIP. Both text-to-image generation and image-to-image transformation are supported by the pipeline.

## Features
* Text-to-Image Generation: Generate images based on text prompts using diffusion and VAE models.
* Image-to-Image Transformation: Modify existing images by adding noise and refining them through a diffusion process.
* Classifier-Free Guidance (CFG): Control the scale of guidance to balance creativity and adherence to the prompt.
* Latent Space Manipulation: Work in the latent space of VAE for efficient image generation.
* Time-Conditioned Diffusion: Use a DDPM (Denoising Diffusion Probabilistic Model) sampler for the diffusion process.

## How It Works
1) VAE Encoder: Encodes input images into a compressed latent space.
2) CLIP: Provides text conditioning by encoding the text prompt into an embedding vector.
3) Diffusion Model: Denoises the latent variables step-by-step using a predefined number of timesteps.
4) VAE Decoder: Decodes the final latent output back into a high-resolution image.

## Model Architecture
* VAE Encoder & Decoder: Used for compressing and reconstructing images.
* CLIP: Maps text into an embedding space for conditioning the diffusion process.
* DDPM Sampler: Handles the diffusion steps and noise addition.

## Setup
Prerequisites
Ensure you have the following installed:

* Python 3.8+
* PyTorch 1.7+
* HuggingFace Tokenizers
* NumPy
* tqdm

## Installation
1) Clone the Repository
2) Install dependencies:

```bash
pip install -r requirements.txt
```
4)  Download the pretrained model weights and place them in the appropriate directory

## Running the Pipeline
To generate images from text prompts:

```bash
python generate.py --prompt "A serene mountain landscape at sunset"
```

To perform image-to-image transformation:

```bash
python generate.py --input_image path_to_image --strength 0.75
```

## Arguments
* --prompt: Text prompt for the generation.
* --input_image: Path to the input image (if performing image-to-image transformation).
* --strength: Strength of the noise added to the input image (range: 0 to 1).
* --cfg_scale: Control the Classifier-Free Guidance scale (default is 7.5

## Performance
* Resolution: Generates images at a resolution of 512x512.
* Inference Time: Approx. 1-2 minutes per image (depending on GPU).

## Customization
You can experiment with different samplers, CFG scales, and model parameters to achieve a variety of artistic results.

## Contributing
Contributions are welcome! Please open issues and submit pull requests for any features, improvements, or bug fixes.

**License**
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.
