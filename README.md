[![Deforum Stable Diffusion](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/deforum/stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb)
![visitors](https://visitor-badge.glitch.me/badge?page_id=deforum_sd_local_repo)
[![Replicate](https://replicate.com/deforum/deforum_stable_diffusion/badge)](https://replicate.com/deforum/deforum_stable_diffusion)

# Deforum Stable Diffusion Local Version

Local version of Deforum Stable Diffusion V0.4, supports txt settings file input and animation features!

- **[Stable Diffusion](https://github.com/CompVis/stable-diffusion) by Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer and the [Stability.ai](https://stability.ai/) Team.**
- **[K Diffusion](https://github.com/crowsonkb/k-diffusion) by [Katherine Crowson](https://twitter.com/RiversHaveWings).**
- **Notebook by [deforum](https://discord.com/invite/upmXXsrwZc)**
- **Local Version by [DGSpitzer](https://www.youtube.com/channel/UCzzsYBF4qwtMwJaPJZ5SuPg) [大谷的游戏创作小屋](https://space.bilibili.com/176003)**
- **Special Thanks to [VIVY Has A Dream](https://github.com/vivyhasadream) for all the help!**

![example](examples/example3.gif)

## 👇Animated Video👇

Made this quick local Windows version mostly based on the Colab code by deforum, which supports very cool turbo mode animation output for Stable Diffusion!

It's tested on:

- Windows 10 with RTX 2080 SUPER and RTX 3090 GPU (it runs somehow much faster on my local 3090 then Colab)
- Windows 10 on CPU with AMD Ryzen 5 (quite slow)
- Windows 10 NVIDIA GTX 1660 Ti (does not currently work, not enough memory - [this does though](https://github.com/sd-webui/stable-diffusion-webui)
- **not tested it on Mac though.**

## Installation

You can use an [miniconda](https://docs.conda.io/en/latest/miniconda.html) environment to host this local project:

```bash
conda create --name dsd python=3.8.5 -y
conda activate dsd
```

And then cd to the cloned folder, run the setup code, and wait for ≈ 5min until it's finished

```python
python setup.py
```

```bash
set PYTORCH_CUDA_ALLOC_CONF=max_split_size_mb:2000
```

## Manually download 3 Model Files

You need to get the `sd-v1-4.ckpt` file and put it on the `./models` folder first to use this. It can be downloaded from [HuggingFace](https://huggingface.co/CompVis/stable-diffusion).

Additionally, you should put `dpt_large-midas-2f21e586.pt` on the `./models` folder as well, [the download link is here](https://github.com/intel-isl/DPT/releases/download/1_0/dpt_large-midas-2f21e586.pt)

There should be another extra file `AdaBins_nyu.pt` which should be downloaded into `./pretrained` folder, [the download link is here](https://cloudflare-ipfs.com/ipfs/Qmd2mMnDLWePKmgfS8m6ntAg4nhV5VkUyAydYBp8cWWeB7/AdaBins_nyu.pt)

## How to use it?

The running command should looks like this:

```python
python run.py --enable_animation_mode --settings "./runSettings_Template.txt"
```

After installation you can try out following examples to see if the code is working

- 1. For generate still images:

```python
python run.py --settings "./examples/runSettings_StillImages.txt"
```

- 2. For animation feature, you need to add `--enable_animation_mode` to enable animation settings in text file:

```python
python run.py --enable_animation_mode --settings "./examples/runSettings_Animation.txt"
```

- 3. For mask feature:

```python
python run.py --settings "./examples/runSettings_Mask.txt"
```

**The output results will be available at `./output` folder.**

All the needed variables & prompts for Deforum Stable Diffusion are set in the txt file (You can refer to the [Colab](https://colab.research.google.com/github/deforum/stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb) page for definition of all the variables), you can have many of settings files for different tasks. There is a template file called `runSettings_Template.txt`. You can create your own txt settings file as well.

That's it!
