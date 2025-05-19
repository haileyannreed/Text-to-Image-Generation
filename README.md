# 🧠 Stable Diffusion: Text-to-Image Generation

This project demonstrates how Stable Diffusion works under the hood by walking through the full pipeline: from a text prompt to a generated image — using PyTorch, Hugging Face 🤗 `diffusers`, and Google Colab.

---

## 🧪 Project Type
**Generative AI** | **Computer Vision** | **Diffusion Models**

---

## 🚀 What is Stable Diffusion?

Stable Diffusion is a **latent text-to-image generation model**. It starts with random noise and gradually denoises it into a realistic image that matches a given text prompt.

Rather than generating full images directly, Stable Diffusion works in **latent space** — creating a compressed representation of the image, which is later decoded.

---

## 🔧 Core Components

| Component      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| **Tokenizer**  | CLIP tokenizer breaks the prompt into token IDs (shape: `(1, 77)`)           |
| **Text Encoder** | CLIP text encoder converts tokens → embeddings `(1, 77, 768)`              |
| **Latent Noise** | Start from pure noise in shape `(1, 4, 64, 64)`                            |
| **U-Net (Diffuser)** | Learns to denoise latent step-by-step, guided by the text embedding   |
| **Scheduler**  | Controls the denoising schedule (DDIM, Euler, etc.)                          |
| **VAE Decoder** | Converts final latent → full-size image `(1, 3, 512, 512)`                  |

---

## 🧬 Full Pipeline (Step-by-Step)

1. **Tokenize the text** prompt → shape `(1, 77)`
2. **Embed with CLIP** → shape `(1, 77, 768)`
3. **Generate random latent noise** → shape `(1, 4, 64, 64)`
4. **U-Net denoising** over 50–100 steps, guided by the prompt
5. **Decode final latent** with VAE → image `(1, 3, 512, 512)`

---

## 🎨 Diffusers Used

This project compares results from **3 different pretrained Stable Diffusion models**:

| Diffuser Model | Style | Link |
|----------------|-------|------|
| `CompVis/stable-diffusion-v1-4` | General-purpose photorealism | [🔗 Hugging Face](https://huggingface.co/CompVis/stable-diffusion-v1-4) |
| `prompthero/openjourney`        | Fantasy / Midjourney-style art | [🔗 Hugging Face](https://huggingface.co/prompthero/openjourney) |
| `SG161222/Realistic_Vision_V4.0` | High-end photorealistic rendering | [🔗 Hugging Face](https://huggingface.co/SG161222/Realistic_Vision_V4.0) |

🔗 Explore other models here: [Text-to-Image Models on Hugging Face](https://huggingface.co/models?pipeline_tag=text-to-image&library=diffusers)

---

## 📸 Example Output

Prompt:  
`"a realistic duck wearing sunglasses sitting on the beach"`

Generated using SD v1.5:
![Generated Duck](INSERT_IMAGE_LINK_HERE)

---

## 📚 Technologies Used

- Python + PyTorch
- Hugging Face `diffusers`, `transformers`
- Google Colab (for GPU acceleration)
- Matplotlib + PIL for visualization

---

## 🧠 Concepts Demonstrated

- CLIP Tokenization and Embedding
- Diffusion models & denoising schedules
- Latent vs. pixel space generation
- Classifier-free guidance
- Prompt engineering for visual generation

---

## 📁 Files in This Project

| File | Description |
|------|-------------|
| `Stable_Diffusion.ipynb` | Full Colab notebook with pipeline and visualizations |
| `README.md` | Project overview and methodology |
| `outputs/` | Folder of sample outputs for different prompts and models |

---

## ✨ Portfolio Significance

This project illustrates:
- My understanding of **Stable Diffusion architecture**
- My ability to break down complex generative AI systems
- Practical experience using **CLIP**, **U-Net**, and **VAE** together

---

## 📬 Contact

Feel free to connect with me if you’d like to collaborate or learn more:
**Hailey Reed**  
🖥️ [GitHub](https://github.com/haileyannreed)  
🌐 [Portfolio](https://haileyannreed.github.io/portfolio)
