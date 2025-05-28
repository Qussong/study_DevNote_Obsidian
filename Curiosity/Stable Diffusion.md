
# Refer
[스테이블 디퓨전 사용법](https://blog.naver.com/jwh7211/223249179037)
[스테이블 디퓨전_설치법](https://blog.naver.com/jwh7211/223247535563)
[스테이블 디퓨전_체크포인트](https://blog.naver.com/PostView.naver?blogId=jwh7211&logNo=223253953953&parentCategoryNo=&categoryNo=6&viewDate=&isShowPopularPosts=false&from=postView)

# CIVITAI
[civitai URL](https://civitai.com/models/1530710/bravo-3d-cartoon)

## 1. BRAVO - 3D Cartoon

🔥 **Key Features:**
- Generates **3D-style characters**, **cartoon scenes**, and **stylized objects** with smooth shapes and pleasing colors
- Perfect for **advertising**, **game assets**, **children's illustrations**, and **social media content**
- Maintains **clean, consistent styling** without artifacts or noise

⚙️ **Technical Specs:**
- **Optimal resolutions:** 640 / 768 / 960
- **Steps:** 20
- **Sampler:** Euler a / Karras
- **CFG Scale:** 5-7 (for soft yet controlled output)

## 2. Fluxmania

File 15.91 GB : checkpoint fp8 (not bf16) with VAE & [**Clip L full fp32**](https://civitai.com/models/1044804/clip-l-full-fp32-zer0int-and-simv4)
Settings : dpmpp_2m - sgm_uniform / cfg 3.5 / steps 25 - 30.
I recommend using this version of [**Clip L**](https://civitai.com/models/1044804/clip-l-full-fp32-zer0int-and-simv4) with the Fluxmania model

**Genuine** : Unet fp16 (no VAE, no clip) / Settings : Euler Simple / cfg 3.5 / steps 30.