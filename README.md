# Image_Restoration_and_Noise_Removal

Team Members <br>
1.Ashal DCunha - 4SO22CD009 <br>
2.Larissa Oshin DSouza - 4SO22CD026 <br>
3.Marishka J Crasta - 4SO22CD031  <br>

## Enhancing Visual Quality in Digital Photography using Image Restoration and Noise Removal Techniques

In the age of smartphone photography and digital images, It's essential to have high-quality visuals that are critical for personal, professional, and commercial use. However, images usually suffer from various degradations such as motion blur, salt-and-pepper noise, and grainy textures due to poor illumination, camera shake, low-quality sensors, or environmental interference or disturbance. These distortions compromise the quality, visual appeal and usability of images, especially in areas like journalism, medical imaging, e-commerce, and historical archiving. This project aims to explore and apply traditional image restoration and noise removal techniques to recover high-quality images from degraded inputs. <br>

## DESCRIPTION OF TECHNIQUES <br>
1. Grainy Image <br>
Grain or digital noise often appears as random speckles in an image, reducing clarity—commonly caused by low-light or high ISO settings. <br>

🔹 Wiener Filter: <br>
A deconvolution technique used to restore images degraded by a known blurring and additive noise. It balances noise suppression with edge preservation using a statistical approach. <br>

🔹 Unsharp Masking: <br>
Enhances edges by subtracting a blurred version of the image from the original. It sharpens fine details, countering grain-induced softening. <br>

🔹 Bilateral Filtering: <br>
Reduces noise while keeping edges sharp by averaging pixels based on both spatial closeness and intensity similarity.
<br> <br>
2. Salt and Pepper Noise <br>
Salt and pepper noise consists of random black and white pixels, typically from transmission errors or sensor faults. <br>

🔹 Median Filtering: <br>
Replaces each pixel with the median of its neighborhood. It's particularly effective for removing isolated noise like salt & pepper while preserving edges. <br>

🔹 Morphological Opening: <br>
Applies erosion followed by dilation using a kernel. Removes small noise dots (pepper) and smoothens objects' contours. <br>

🔹 Non-Local Means Denoising (NLM): <br>
Uses patch similarity across the entire image to reduce noise, maintaining fine texture and detail—especially effective in low-frequency areas. <br>
<br>
3. Blurred Image <br>
Blur is caused by motion, defocus, or camera shake and leads to loss of detail. <br>

🔹 Wiener Filter: <br>
Reconstructs a sharper version from a blurred image using a blur kernel and estimated noise. <br>

🔹 Unsharp Masking: <br>
Sharpens blurred images by enhancing contrast at edges—ideal for boosting image details lost due to blur. <br>

🔹 Bilateral Filtering: <br>
Helps sharpen slightly blurred regions while maintaining smooth transitions and reducing noise. <br>
<br>
4. Saturation Enhancement <br>
Saturation refers to the intensity of colors in an image. Enhancing it makes images look more vivid and vibrant. <br>

🔹 HSV Color Space Manipulation: <br>
Convert the image to HSV, increase the saturation (S) channel, clip values to prevent overflow, and convert back to BGR. This enhances color richness without affecting brightness or hue. <br>
<br>

## PROGRAM FLOW

Start
   Step 1: Load input images (Grainy, Salt & Pepper, Blurred, Low Saturation)
   Step 2: Preprocess image if required (resize, normalize)
   Step 3: Apply restoration/enhancement techniques:
         Grainy: Wiener → Unsharp → Bilateral\
         Salt & Pepper: Median → Morphological Opening → Non-local Means
         Blur: Wiener → Unsharp → Bilateral
         Saturation: HSV Manipulation
   Step 4: Evaluate outputs using:
         PSNR (Peak Signal-to-Noise Ratio)
         SSIM (Structural Similarity Index)
   Step 5: Display results side-by-side using matplotlib
End
