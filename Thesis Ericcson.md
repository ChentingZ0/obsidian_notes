[paper](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)
[3D Gaussian Splatting](https://www.youtube.com/watch?v=HVv_IQKlafQ&ab_channel=IndividualKex)
Integrating Real-time BIM with Gaussian Splatting for Seamless Object Identification.

- **BIM**: Building information modeling 
Digital representations of the physical and functional characteristics of places.
Digital twins, CAD

Traditional pipeline: 
photogrammetry, Ray tracing, path tracing or diffusion
**Ray tracing** is an advanced way of rendering light and shadows in a scene.

**Rasterization** technique utilized for rendering photorealistic scenes.
It falls under the category of Radiance Fields, much like Nerfs.
Rasterize refers to the process of converting a vector-based image or object into a raster or bitmap format

**BMP** file format, bitmap: raster graphics image file format used to store bitmap digital images.

- ***Radiance Fields***:
Refer to a concept in computer graphics and computer vision. A radiance field is a 3D representation of the radiance, which describes the amount of light that travels in a particular direction through a point in space.

Radiance fields are often employed in ray tracing and path tracing algorithms to simulate how light interacts with surfaces and materials in a virtual environment.

***NeRF***
Neural radiance field, a fully-connected neural network that can generate novel views of complex 3D scenes, based on a partial set of 2D images.

- **Gaussian Splatting**
Start with a sequence of photos taken at different angles from a subject, can also be extracted from a video as an image sequence.

![[Pasted image 20231205193939.png]]
1. ***SfM***: Structure-from-Motion
-> To form the 3D point cloud
![[Pasted image 20231205200213.png]]
2. -> Then each point is turned into a Gaussian.
In 3D space these gaussians take the shape of ellipsoid.(multivariate)

3. -> Then the Gausian enter an iterative optimization process. These Gaussians get fine-tuned constantly to match the original photos that we took by adjusting their 3D positions, color, opacity and how their details vary from different directions.

4. To view these Gaussians, we use a technique called ***rasterization*** which projects them onto a 2D surface.

5. Training: Adjust the values of the Gaussians so that they produce images they look like the original images. A lot like training a neural network but with zero layers. The training uses ***adaptive density control***:
	automated densification and pruning. When a Gaussian is too transparent, it gets removed or when a Gaussian is too big, it splits into two.

In computer graphics, rasterization is the task of taking an image described in a vector graphics format and converting it into a raster image. The rasterized image may then be displayed on a computer display, video display or printer, or stored in a bitmap file format. 

Consider the distance from the viewer for depth and then for each pixel, we'll calculate how much each Gaussian contributes to that pixel. With all these ingredients, we tend to end up with a quality that is better than the other Radiance field approaches


- **Goal**
Investigate and compare current research regarding the usage of BIM and visualizations with Gaussian Splatting

Implement an object recognition system to identify objects/assets in a Gaussian Splatting/BIM.

Implement a position recognition system identify the position objects/assets in a Gaussian Splatting/BIM.

Analyze results of the tests and evaluate the outcome of the systems.
