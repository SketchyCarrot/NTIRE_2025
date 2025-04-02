# Denoising Images using DnCNN followed by Non-Local Means
Project made for NTIRE Denoising Challenge

This project implements Denoising Convolutional Neural Networks (DnCNN) architeture from the paper Kai Zhang et al., "Beyond a Gaussian Denoiser: Residual Learning of Deep CNN for Image Denoising."

### 1. Data Used
1. DIV2K dataset downloaded from kaggle.
2. Added noise level 50 to create artificial noisy dataset.

### 2. Architecture
1. The DnCNN model has a depth of 12 layers.
2. After the trained model maked a prediction, Non Local Means denoising method is applied for further refinement of the image.
![image](https://github.com/user-attachments/assets/9445cf7b-9614-4d52-9c80-eaa13c282a2e)

### 3. Training
1. Trained the model on rescaled images of dimensions (1536, 1536, 3).
2. The train and validation images were divided into patches of size 256x256 before being fed to the model, making the load easier on the machine.
3. The model ```tf_denoiser_2.h5``` gives the best results.

### 4. Testing
1. The test images were split into patches of size 256x256 and then reassembled after denoising to create the full image.
2. Patch overlapping was also implemented to handle images of odd dimensions.
3. Below are some before and after images.
![output4](https://github.com/user-attachments/assets/dfded838-af6b-4cca-b3bf-14b974288ee3)
![output3](https://github.com/user-attachments/assets/a68f75ab-1b81-4860-95cf-6ab2395d7e51)
![output2](https://github.com/user-attachments/assets/abf10786-57a8-4d28-bbd6-47344556929a)

### 5. Validation
On the validation set of DIV2K dataset,
PSNR = 26.52
SSIM = 0.7537




