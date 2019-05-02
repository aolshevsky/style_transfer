# Style Transfer

<h3 align="center">
  <img src="assets/header.png" width="300">
</h3>

Style Transfer is a process in which we strive to modify the style of an image while preserving its content. Given an input image and a style image, we can compute an output image with the original content but a new style.

# How does it work?
1. We take input image and style images and resize them to equal shapes.
2. We load a pre-trained CNN (VGG16).
3. Knowing that we can distinguish layers that are responsible for the style (basic shapes, colors etc.) and the ones responsible for the content (image-specific features), we can separate the layers to independently work on the content and style.
4. Then we set our task as an optimization problem where we are going to minimize:
	* **content loss** (distance between the input and output images - we strive to preserve the content)
	* **style loss** (distance between the style and output images - we strive to apply a new style)
	* **total variation loss** (regularization - spatial smoothness to denoise the output image)
5. Finally, we set our gradients and optimize with the [L-BFGS](https://en.wikipedia.org/wiki/Limited-memory_BFGS) algorithm.

## Examples

<h3>
  <img src="assets/results/city_result_feathers_2.jpg">
</h3>

<h3>
  <img src="assets/results/city_result_the_scream_2.jpg">
</h3>

<h3>
  <img src="assets/results/my_cat_result.jpg">
</h3>

<h3>
  <img src="assets/results/my_cat_result_frida_kahlo_2.jpg">
</h3>

<h3>
  <img src="assets/results/city_result_candy.jpg">
</h3>

<h3>
  <img src="assets/results/city_result_starry_night_crop_2.jpg">
</h3>
