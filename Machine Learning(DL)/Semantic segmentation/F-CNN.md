### Fully connected neural network
[medium](https://towardsdatascience.com/review-fcn-semantic-segmentation-eb8c9b50d2d1)
- **In Classification**:
An input image is downsized, and goes through convolution layers and fully connected layers, and output one predicted label for the input image.
![classification](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ErOVnlmtWYFGpnpvKJImKw.png)


- **In Semantic Segmentation**
Single label ×   ->   label map (pixelwise output)   √
If we upsample the output, we can calculate the pixelwise output
![upsample](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*LtSSJ9QP0Y9qWG9nz9sb2w.png)

![feature map](https://miro.medium.com/v2/resize:fit:750/format:webp/1*NXNGhfSyzQcKzoOSt-Z0Ng.png)


- Upsampling via Deconvolution (Up convolution, transposed convolution)
Convolution is a process getting the output size smaller. Thus, the name, deconvolution, is coming from when we want to have upsampling to get the output size larger.
![process](https://miro.medium.com/v2/resize:fit:640/format:webp/0*NBKHZlXvqOg3R6_z.gif)

- **Fusing the Output**
After going through conv7 as below, the output size is small, then 32× upsampling is done to make the output have the same size of input image. But it also makes the output label map rough. And it is called **FCN-32s**:
![FCN-32](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ajovnrcLYRuwlTrM5j-Qng.png)

This is because, ==**deep features can be obtained when going deeper, spatial location information is also lost when going deeper**==**.** That means output from shallower layers have more location information. If we combine both, we can enhance the result.

To combine, we **fuse the output (by element-wise addition)**:
![fuse](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*lUnNaKAjL-Mq10v3tIBtJg.png)

**FCN-16s**: The output from pool5 is 2× upsampled and fuse with pool4 and perform 16× upsampling. Similar operations for **FCN-8s** as in the figure above.

![FCNs](https://miro.medium.com/v2/resize:fit:828/format:webp/1*tcYqvV0KHjK2ANBGe8GpjQ.png)
**FCN-32s result is very rough due to loss of location information** while FCN-8s has the best result

This fusing operation actually is just like the boosting / ensemble technique used in AlexNet, VGGNet, and GoogLeNet, where they add the results by multiple model to make the prediction more accurate. But in this case, it is done for each pixel, and they are added from the results of different layers within a model.