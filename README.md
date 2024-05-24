# Red Blood Cell Counter
 This repository contains the implementation of a red blood cell counting application

This project is part of the CSC209H1 F course at the University of Toronto, focusing on system-level programming. The assignment challenges students to implement a simple red blood cell counting application using basic image processing techniques on text-formatted image data.

## Table of Contents
- [Introduction](#introduction)
- [Setup](#setup)
- [Usage](#usage)
- [Functionalities](#functionalities)
  - [Reading Image Data](#reading-image-data)
  - [Counting Cells](#counting-cells)
- [Testing](#testing)
- [Submission](#submission)
- [License](#license)

## Introduction

In this assignment, students will analyze blood smear images stored in a simplified black and white BMP format, where pixels are represented as 0 (black) or 255 (white). The goal is to develop a program that counts the number of red blood cells in such images, based on connectivity of white pixels.

## Setup

1. Clone the repository and navigate to the project directory:
   ```bash
   git clone <repository-url>
   cd <project-directory>
   ```
2. Compile the program using GCC:
   ```bash
   gcc -Wall -g -std=gnu99 -o count_cells count_cells.c image.c
   ```

## Usage

To run the program, use:
```bash
./count_cells <image-file.txt> [-p]
```
- `<image-file.txt>` is the path to the text file containing the image data.
- `-p` is an optional argument to print the pixel matrix before other program outputs.

## Functionalities

### Reading Image Data

The program reads image data from a text file specifying the dimensions and pixel values:
- `read_image(int num_rows, int num_cols, int arr[num_rows][num_cols], FILE *fp)` reads the image data into an array.
- `print_image(int num_rows, int num_cols, int arr[num_rows][num_cols])` prints the pixel matrix.

### Counting Cells

Using the flood fill algorithm, the program counts discrete groups of connected white pixels (cells):
- `count_cells(...)` counts the cells based on adjacency of white pixels.
- Outputs the count using the format "Number of Cells is %d\n".

## Testing

You are encouraged to create small test image files to validate the functionality of the program and check edge cases. Example input format:
```text
4 7
0 0 255 255 0 0 0
0 255 0 0 255 255 0
0 255 0 0 0 0 0 
255 255 0 0 0 0 0
```
This should help verify the accuracy of the cell counting algorithm.

## Submission

Add, commit, and push your `image.c` and `count_cells.c` files to the `a1` directory in your repository:
```bash
git add image.c count_cells.c
git commit -m "Add cell counting functionality"
git push
```
Please refer to the Syllabus for detailed submission guidelines.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
