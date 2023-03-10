# CTR ESTIMATION: METHODOLOGY AND IMPLEMENTATION DETAILS
The methodology that we used for the CTR estimation, is shown in the following figure.
<img width="532" alt="metodo" src="https://user-images.githubusercontent.com/94172910/209103139-a995ffed-fa8e-43ed-8a92-85f2cec41de6.PNG">

**FOR THE LUNG SEGMENTATION TASK:**

Some modifications to the U-Net with VAE architecture from the official implementation of the work by Selvan et. al [1] have been done, to allow the output of the
model to have a field of view wider of 128 pixels on each side with respect to the field of view of the input image, in order to handle clipped anatomy cases. The proposed method has been trained and validate on a total of 704 images from Montgomery and Shenzhen dataset.

Augmentation techniques have been widely used: mainly rotation, flipping, block and diffuse mask augmentation and clipping augmentation.
During the training a batch size of 12 was used, with a learning rate of 10−4, with Adam optimizer for a maximum of 200 epochs. A composed loss function with binary cross-entropy and KL divergence loss was used. 

<img width="817" alt="unet2_ (1)" src="https://user-images.githubusercontent.com/94172910/209103761-8d7a2fb4-4d96-4cb0-a8b8-96536c8e177e.PNG">

**FOR THE CTR CALCULATION:**

The CTR is then calculated as the radio between the cardiac diameter and the thoracic diameter extracted from the lung masks and defined as follow:
- cardiac diameter: searched above the vertex of the cardiophrenic angle of the right lung. It is defined as the maximum horizontal distance between the two lungs.

- thoracic diameter: defined as the maximum distance between the rightmost and the leftmost point on the lung segmentation chosen on the same horizontal line.


<img width="200" alt="ctr" src="https://user-images.githubusercontent.com/94172910/209111151-bce86648-7cd3-422f-a1c1-7969a8c149df.png">


[1] _R. Selvan, E. B. Dam, N. S. Detlefsen, S. Rischel, K. Sheng, M. Nielsen,
and A. Pai, “Lung segmentation from chest x-rays using variational data
imputation,” 2020_
