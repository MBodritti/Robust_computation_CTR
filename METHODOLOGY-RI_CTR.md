# METHODOLOGY AND IMPLEMENTATION DETAILS
The methodology that we used for the RI_CTR estimation, is shown in the folling figure.

![image](https://user-images.githubusercontent.com/94172910/209105900-4d90280c-ac65-4456-b8b4-79a15955b4cd.png)

The lung segmentation model described in METHODOLOGY-CTR was modified to allow multi-label outputs. The already trained lung segmentation model was fine-tuned with heart segmentation masks from Wingspan dataset. 
With this approach one U-Net with wider output with VAE was used to obtain both lungs and heart segmentation masks.

<img width="884" alt="UNET_multi (1)" src="https://user-images.githubusercontent.com/94172910/209106468-49de3873-c0de-49f9-b9cf-7f0eefacd523.PNG">

During the training a batch size of 12 was used, with a learning rate of 10−4, with Adam optimizer for a maximum of 200 epochs. A composed loss function with multiple  binary cross-entropy and KL divergence loss was used. The multiple-binary cross-entropy was the sum of the binary cross-entropy for lung mask prediction task and the
binary cross-entropy for heart mask prediction task.
