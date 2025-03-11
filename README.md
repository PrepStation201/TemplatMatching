# TemplatMatching
# Template Matching in OpenCV (Custom Implementation)

## 📌 What is Template Matching?
Template Matching is a technique in computer vision used to find a small object (template) within a larger image. The process involves sliding the template over the input image and calculating a similarity score at each position to determine the best match.

There are different ways to compute similarity, including:
- **Normalized Cross-Correlation (NCC)** – Measures how similar two images are by comparing pixel intensity patterns.
- **Sum of Squared Differences (SSD)** – Measures the difference between the template and the image region.
- **Mean Squared Error (MSE)** – Calculates the average squared differences between pixel values.

## 🔹 How This Code Works
This implementation performs **template matching using NCC** without relying on OpenCV's `cv2.matchTemplate()`. Instead, it follows these steps:

### 🛠 **Code Flow**
1. **Read and Resize Images:**  
   - The input image (`soccer_practice.jpg`) and the template (`ball.PNG`) are loaded in grayscale mode.  
   - Both images are resized for better processing.

2. **Define `template_matching()` Function:**  
   - A **sliding window** approach is used to scan the input image with the template.  
   - For each possible position, the similarity score is computed using **Normalized Cross-Correlation (NCC)**.  

3. **Compute NCC for Each Position:**  
   - The algorithm extracts a small **region of interest (ROI)** from the input image that matches the template size.  
   - It calculates the **NCC score** to measure similarity:
     - Subtracts the mean intensity from both the ROI and the template.  
     - Computes the correlation between both.  
     - Normalizes the score to avoid scale dependency.  
   - The location with the **highest NCC score** is considered the best match.  

4. **Draw a Bounding Box Around the Best Match:**  
   - The **coordinates of the best match** are used to draw a **rectangle** around the detected object.  

5. **Display the Result:**  
   - Since OpenCV’s `cv2.imshow()` doesn’t work in Google Colab, the **`cv2_imshow()`** function is used to display the image with the detected template.  

## 🎯 **Why Use This Approach?**
✔ Fully **custom template matching** without OpenCV's built-in `cv2.matchTemplate()`.  
✔ **Better understanding** of how template matching works internally.  
✔ **Can be extended** to use different similarity measures like SSD or MSE.  
✔ Works in **Google Colab** without GUI errors.  

This project is useful for **object detection**, **pattern recognition**, and **image processing** tasks. 🚀  

