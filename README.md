## Lab 1 - MATLAB Installation and Basic Image Processing
This lab involved installing MATLAB, a programming and numerical computing platform widely used for engineering and scientific applications. The lab also introduced basic geometric transformations, such as rotation and shearing, by manipulating 2D image data.

### MATLAB Installation
Installing MATLAB was straightforward. We accessed the MathWorks website and downloaded the software using our university credentials.

### Loading a Grayscale Image
Once MATLAB was set up, the first task was to load a grayscale image called clown. Initially, the load function was used _load clown_

Load Output:

<p align="center">
  <img src="https://github.com/user-attachments/assets/e92ff6b8-a8aa-4cad-b283-d4d3ede42da6" alt="image">
</p>

However, this approach resulted in an issue where the image did not load properly due to format and naming issues. The image was stored as a 200×320 matrix of grayscale values ranging from 0 to 1.

### Retrieving a Specific Pixel Value

To find the grayscale value of a specific pixel, I initially encountered an error. This was resolved by using the imread function to correctly load the image and the im2double function to convert it from uint8 (0–255) to double precision (0–1). The following code successfully retrieves the grayscale value at coordinates (319, 20):

```
img = imread('clown.png');  
img = im2double(img);  
pixel_value = img(20, 319);  
disp(pixel_value);
```

In my case, the grayscale value at (319,20) was 0.1686.

### Displaying the Image
To visualize the image, the _imshow_ function was used:

```
imshow(img);
```

This function displays the grayscale image, making it easier to analyse and apply further transformations.

### Task 1 - Image Rotation

The goal of this task was to implement a function that rotates a grayscale image by a given angle (Theta) while ensuring that the output image maintains the same dimensions as the original. The rotation was to be performed about the center of the image, using the nearest neighbor interpolation method, and any pixels mapped outside the image boundary should be painted black.


