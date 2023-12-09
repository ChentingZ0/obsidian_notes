![U-net](https://media.geeksforgeeks.org/wp-content/uploads/20220614121231/Group14.jpg)
[geeks](https://www.geeksforgeeks.org/u-net-architecture-explained/)

The contracting path in U-Net is responsible for identifying the relevant features in the input image. 

The encoder layers perform convolutional operations that **reduce the spatial resolution of the feature maps while increasing their depth**. Thereby capturing increasingly abstract representations of the input.(Downsampling)

The decoder layers in the expansive path upsample the feature maps, while also performing convolutional operations.(Upsampling)

