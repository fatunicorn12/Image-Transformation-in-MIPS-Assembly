Image Processing in MIPS Assembly
Overview:
This repository contains MIPS Assembly code for performing basic image processing tasks, including image thresholding, matrix transformation, and simple image cryptography. The code is divided into three main parts, each serving a distinct function:

Converts an image into a binary (black and white) image based on a given threshold value.
Applies a linear transformation matrix to an image, altering its spatial properties.
Image Cryptography: Implements a simple encryption technique by manipulating pixel positions based on modular arithmetic.
Code Structure

1. Image Thresholding
This section of the code takes an image and converts it into a binary image by comparing each pixel's value with a specified threshold. Pixels above the threshold are set to white (0xFF), while those below are set to black (0x00).

Inputs:
a0: Input buffer address (source image)
a1: Output buffer address (thresholded image)
a2: Image dimension (assumed to be square, i.e., number of pixels = a2 * a2)
a3: Threshold value

Process:
Iterates through each pixel, compares it to the threshold, and assigns it a black or white value.
2. Matrix Transformation
This section performs a linear transformation on the image using a provided transformation matrix. The matrix alters the spatial arrangement of the pixels, which can be used for operations like scaling, rotation, or shearing.

Inputs:

a0: Input buffer address (source image)
a1: Output buffer address (transformed image)
a2: Transformation matrix address
a3: Image dimension (assumed to be square, i.e., number of pixels = a3 * a3)
Process:

Multiplies each pixel's coordinates by the transformation matrix to compute new positions, then stores the transformed pixel in the output buffer.
3. Image Cryptography
This section of the code implements a basic cryptography technique by modifying the pixel positions based on a remainder operation with a divisor of 5. The new positions are determined based on the remainder, creating a pseudo-random scrambling of the image.

Inputs:
a0: Input buffer address (source image)
a1: Output buffer address (encrypted image)
a2: Image dimension (assumed to be square, i.e., number of pixels = a2 * a2)
Process:

Computes new pixel positions based on the remainder of the pixel index divided by 5 and stores the pixel in the corresponding output buffer position.
How to Use:
Assemble and Run: Use a MIPS assembler and simulator to compile and run the code. Ensure that the input image is loaded into memory at the specified input buffer address (a0).
Modify Parameters: Adjust the threshold, transformation matrix, or image dimensions as needed to see different results.
Analyze Output: The output buffers (a1) will contain the processed image data, which can be analyzed or converted back into an image format using additional tools.

Requirements:
MIPS Assembler and Simulator (e.g., MARS, SPIM)
Image data formatted as a square matrix of pixel values

Future Enhancements:
Implement more advanced image processing techniques, such as edge detection or blurring.
Expand the cryptography section to include more sophisticated encryption algorithms.
Optimize the code for better performance on large images.

License
This project is open-source and available under the MIT License.
