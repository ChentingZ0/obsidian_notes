**Spatial techniques**:
- Histogram equalization
Histogram: it represents the number of pixels for each intensity value.

Improve contrast in images -> stretching out the intensity range of the image.

Linear Image Processing
g = HyT f Hx
- Image averaging for noise reduction(average)
- Subsampling: size reduction, sharpening

**Frequency techniques**:
- DFT: transfer to frequency domain
Low-pass filter, high-pass filter

- *Wiener filter*
The signal of interest may be corrupted by additive noise. The Wiener filter can be used to filter out the noise from the corrupted signal to provide an estimate of the underlying signal of interest by designing a filter that could minimize mean squared error.

Assumption: signal and (additive) noise are stationary linear stochastic processes with known spectral characteristics or known autocorrelation and cross-correlation.
(above project 1)

**Image compression** :(project 2)
If not compression, frame size: $176\times144$ , every pixel with 8 bit, the bit rate is given by:
$R = 30 \times (176\times144\times8) = 6117 kps$
- *DCT*
Discrete Cosine Transformation
Used in JPEG 2000 standards.

- *Lifting scheme - DWT(discrete wavelet transform)*
The lifting scheme is an alternative technique for performing the DWT using biorthogonal wavelets.

Steps:
1. Split input signal into even samples and odd samples signals.
2. Use Analysis filter bank to separate the high-frequency coefficient and the low-frequency coefficients.
3. Use Synthesis filter bank to reconstruct even and odd samples. 

It allows for perfect reconstruction


**Information theory:**
- Entropy: how much information contained in this event

- Mutual information: I(X;Y) = H(X) - H(X|Y). How much uncertainty X reducted after the observation of Y

- Rate distortion theory
lossy compression -> lower the bit rate R by allowing some acceptable distortion D of the signal.

- Quantizer
Lloyd-Max Scalar Quantizer
Uniform quantizer

- 6dB rule of thumbs: 
This rule states that for each bit you add to a signal, you add 6 dB of signal to noise ratio.

**Video coders** (project 3):
1. Intra-Frame video coder
Process the video frame by frame, exploit the spatial redundancy. 

2. Conditional replenishiment video coder
Exploit temporal redundancy
Copy mode: copy a block from the previous block in the previous frame.

3. Video coder with motion compensation
When a sequence of frames contains moving objects, directly copying will introduce loss. Motion compensation is introduced to track movements.

Motion vector searches for the most similar block of the previous frame. Use SSD(sum of squared difference).

-> predicted frame -> residual (what we encode) 

4. Rate calculation