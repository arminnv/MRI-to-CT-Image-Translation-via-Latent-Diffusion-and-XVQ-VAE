# MRI-to-CT Translation with Shared-Latent VQ-VAE and Latent Diffusion

PyTorch code for **MRI-to-CT image translation** using a two-stage latent generative pipeline. The project first learns MRI/CT representations with a VQ-VAE-style autoencoder and then trains a conditional latent diffusion model to synthesize CT latents from MRI. The diffusion U-Net supports early MRI conditioning by latent concatenation and bottleneck cross-attention.

## Method

1. **Shared-latent VQ-VAE** — learns compact MRI and CT representations and explores shared/private latent structure across the two modalities.
2. **Conditional latent diffusion** — corrupts the CT latent with diffusion noise and predicts the denoising direction while conditioning on the MRI latent.
3. **MRI cross-attention** — projects the MRI latent into the U-Net bottleneck and uses multi-head cross-attention in addition to input concatenation.
4. **CT reconstruction** — the denoised CT latent is decoded back to image space with the CT decoder.



## Sample MRI → CT result


![Sample MRI-to-CT translation](results/samples/x0_0.png)


