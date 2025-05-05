# Image_Restoration_and_Noise_Removal

## Team Members

- Ashal DCunha - 4SO22CD009  
- Larissa Oshin DSouza - 4SO22CD026  
- Marishka J Crasta - 4SO22CD031  

## Enhancing Visual Quality in Digital Photography using Image Restoration and Noise Removal Techniques

In the age of smartphone photography and digital images, it's essential to have high-quality visuals that are critical for personal, professional, and commercial use. However, images usually suffer from various degradations such as motion blur, salt-and-pepper noise, and grainy textures due to poor illumination, camera shake, low-quality sensors, or environmental interference. These distortions compromise the quality, visual appeal, and usability of images, especially in areas like journalism, medical imaging, e-commerce, and historical archiving. This project aims to explore and apply traditional image restoration and noise removal techniques to recover high-quality images from degraded inputs.

## DESCRIPTION OF TECHNIQUES

**1. Grainy Image**  
Grain or digital noise often appears as random speckles in an image, reducing clarity—commonly caused by low-light or high ISO settings.

- **Wiener Filter:**  
  A deconvolution technique used to restore images degraded by a known blurring and additive noise. It balances noise suppression with edge preservation using a statistical approach.

- **Unsharp Masking:**  
  Enhances edges by subtracting a blurred version of the image from the original. It sharpens fine details, countering grain-induced softening.

- **Bilateral Filtering:**  
  Reduces noise while keeping edges sharp by averaging pixels based on both spatial closeness and intensity similarity.

---

**2. Salt and Pepper Noise**  
Salt and pepper noise consists of random black and white pixels, typically from transmission errors or sensor faults.

- **Median Filtering:**  
  Replaces each pixel with the median of its neighborhood. It's particularly effective for removing isolated noise like salt & pepper while preserving edges.

- **Morphological Opening:**  
  Applies erosion followed by dilation using a kernel. Removes small noise dots (pepper) and smoothens objects' contours.

- **Non-Local Means Denoising (NLM):**  
  Uses patch similarity across the entire image to reduce noise, maintaining fine texture and detail—especially effective in low-frequency areas.

---

**3. Blurred Image**  
Blur is caused by motion, defocus, or camera shake and leads to loss of detail.

- **Wiener Filter:**  
  Reconstructs a sharper version from a blurred image using a blur kernel and estimated noise.

- **Unsharp Masking:**  
  Sharpens blurred images by enhancing contrast at edges—ideal for boosting image details lost due to blur.

- **Bilateral Filtering:**  
  Helps sharpen slightly blurred regions while maintaining smooth transitions and reducing noise.

---

**4. Saturation Enhancement**  
Saturation refers to the intensity of colors in an image. Enhancing it makes images look more vivid and vibrant.

- **HSV Color Space Manipulation:**  
  Convert the image to HSV, increase the saturation (S) channel, clip values to prevent overflow, and convert back to BGR. This enhances color richness without affecting brightness or hue.

---

## PROGRAM FLOW
Start <br>
   Step 1: Load input images (Grainy, Salt & Pepper, Blurred, Low Saturation) <br>
   Step 2: Preprocess image if required (resize, normalize) <br>
   Step 3: Apply restoration/enhancement techniques: <br>
         Grainy: Wiener → Unsharp → Bilateral  <br>
         Salt & Pepper: Median → Morphological Opening → Non-local Means <br>
         Blur: Wiener → Unsharp → Bilateral  <br>
         Saturation: HSV Manipulation  <br>
   Step 4: Evaluate outputs using:  <br>
         PSNR (Peak Signal-to-Noise Ratio)  <br>
         SSIM (Structural Similarity Index)  <br>
   Step 5: Display results side-by-side using matplotlib  <br>
End  <br>
