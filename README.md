# Overview
This is a simple pixel blending challenge which could benefit from multithreading, SIMD and even GPGPU like CUDA!

# Input file
1. Input file is an image file in .PPM (Portable Pix Map) extension. 
More info on PPM here - https://www.cs.swarthmore.edu/~soni/cs35/f13/Labs/extras/01/ppm_info.html
* For this challenge, we will restrict the first header line to be "P3" and the max color range to be 255.
2. The image file is of size a x b. (a is the column pixel count and b is the row pixel count)
3. The image can be thought of as a "spritesheet", a list of images of size a x c combined into one. (where "b" is a multiple of "c")
* We will refer to each image within the "spritesheet" as a "sub-image"

Example:

![Sample input image](/sample/input.png)

# Output file
1. Output file is also an image file in .PPM extension.
2. The image file should be of size a x c (where "b" is dividable by "c" )
3. Calculate the pixel values by doing the followings:
* Declare a variable "result" which is a 2D array of 3D vector. Initialise it with the size a x c and all zero values. This array will contain the final pixel outputs for the output file.
* Do a "n" number of loop where "n" is the number of "sub-images" in the input file.
* Within each loop, update "result" by doing the following calculation:
```
result.r = result.r * 0.5 + subimage[index].r * 0.5
result.g = result.g * 0.5 + subimage[index].g * 0.5
result.b = result.b * 0.5 + subimage[index].b * 0.5
```
* index is the loop iteration number
* subimage[index] refers to the sub-image within the input file where the pixel starts from x: 0 and y: "c" x "index".







