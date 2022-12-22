# RI_CTR ESTIMATION: METHODOLOGY AND IMPLEMENTATION DETAILS
The methodology that we used for the RI_CTR estimation, is shown in the following figure.
<img width="395" alt="met2" src="https://user-images.githubusercontent.com/94172910/209112124-b8863e9d-e786-4862-9666-d6f47bf508d0.PNG">

**FOR THE LUNG AND HEART SEGMENTATION TASK:**

The lung segmentation model described in METHODOLOGY-CTR was modified to allow multi-label outputs. The already trained lung segmentation model was fine-tuned with heart segmentation masks from Wingspan dataset. 
With this approach one U-Net with wider output with VAE was used to obtain both lungs and heart segmentation masks.

During the training a batch size of 12 was used, with a learning rate of 10−4, with Adam optimizer for a maximum of 200 epochs. A composed loss function with multiple  binary cross-entropy and KL divergence loss was used. The multiple-binary cross-entropy was the sum of the binary cross-entropy for lung mask prediction task and the
binary cross-entropy for heart mask prediction task.

<img width="884" alt="UNET_multi (1)" src="https://user-images.githubusercontent.com/94172910/209106468-49de3873-c0de-49f9-b9cf-7f0eefacd523.PNG">



**FOR THE RI_CTR CALCULATION**:

The RI_CTR is then calculated as the radio between the cardiac diameter and the thoracic diameter extracted from the anatomical segmentation masks and defined as follow:

- cardiac diameter: diameter of the maximum circle inscribed in the heart masks

- thoracic diameter: maximum horizontal width of the rotated lungs. Lungs have been rotated to obtain consistent orientation.

<img width="286" alt="rictr" src="https://user-images.githubusercontent.com/94172910/209111923-9d7ae306-1920-42e0-baa3-f3d0dc0677a6.PNG">
