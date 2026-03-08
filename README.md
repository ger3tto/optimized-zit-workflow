# An optimized ZIT Workflow

This ComfyUI Workflow is designed around Z-Image-Turbo (ZIT for short)
For me, it generates images in 5 minutes. 
I, however, do this on decade old hardware.
For any assistance, DM @ger3ttothe2nd on Discord or @gerrydoestech on TikTok

My specs:
GTX 1060 6GB
i7-4790
16GB of DDR3
Rest is basically irrelevant for generation

# Why's it different from other workflows?

Mine is organized, cable managed.
In other words, no wire spaghetti

# How it works
Base generation at 448x672, upscaled 1.5x in latent space before 
a light refinement pass. Face and hand detailers run before final 
RealESRGAN upscaling and a slight downscale to remove artifacts. 
Final output: ~2419x3629.

# Where files go:

Z-Image-Turbo goes in /models/unet
ae.sft goes into /models/vae
Qwen3 4B goes into /models/clip
The rest is downloaded inside ComfyUI Manager.

# Requirements

1: Z-Image-Turbo in Q4_K_S format. Download [here](https://huggingface.co/unsloth/Z-Image-Turbo-GGUF/resolve/main/z-image-turbo-Q4_K_S.gguf?download=true)
2: ae.sft Download [here](https://cnb.cool/Tianzi2025/comfyui_models/-/lfs/afc8e28272cd15db3919bacdb6918ce9c1ed22e96cb12c4d5ed0fba823529e38?name=ae.sft)
3: Qwen3 4B. You can either use your own, or use [this](https://huggingface.co/BennyDaBall/Qwen3-4b-Z-Image-Engineer-V4/resolve/main/Qwen3-4b-Z-Image-Engineer-V4-Q4_K_S.gguf)
4: An upscaling model. I personally use RealESRGAN-4x. You can choose whatever you want.

# Custom nodes used:

ComfyUI-GGUF (ID 8)
ComfyUI Impact Pack + Subpack (IDs 11 and 203)
rgthree-comfy (ID 14)
