# Nailfold Capillary Detection and Counting Method

## Overview

This repository showcases a challenging project from the "Medical Image Analysis" course: the detection and counting of nailfold capillaries without using Machine Learning or Deep Learning techniques. The focus is strictly on traditional image processing methods, providing a unique perspective in a field often dominated by modern algorithmic approaches.

## Challenge

The task was to develop a method that relies solely on image processing techniques to detect and count nailfold capillaries, which is crucial for medical diagnostics. This constraint was set to encourage a deeper understanding of fundamental image analysis methods and to explore their potential in applications where machine learning may not be viable.

## Dataset

The dataset includes images from four distinct classes: two healthy individuals (N1 and N2) and two with disease (S1 and S2), making up a total of 30 images. The dataset's complexity is heightened due to varying conditions like illumination and rotation, which simulate real-world challenges in medical imaging.

## Methodology

My method for counting capillaries in images adheres to a two-stage process: preprocessing and processing.

### Preprocessing Stage
- **Channel Selection**: Starting with a full-color image, I select the green channel, which is most indicative of capillary presence.
- **ROI Detection**: Utilizing Gaussian blur smoothens the image, which is then followed by Canny edge detection to highlight edges. A Hough line transformation identifies the longest line, which guides the image rotation and ROI extraction.

### Processing Stage
- **Image Enhancement**: To increase the visibility of capillaries, I employ histogram equalization and Contrast Limited Adaptive Histogram Equalization (CLAHE), adjusting the parameters to the image's luminance.
- **Capillary Detection**: Morphological operations and thresholding techniques are applied to the enhanced image. I then identify contours, classify them as capillaries based on their tubular shape, and disregard any horizontal structures by fitting ellipses to the contours and examining the angle of the major axis.

### Analysis and Counting
- **Contour Analysis**: Each contour is analyzed for its geometrical properties. Ellipses are fitted to determine if a contour represents a capillary, based on its orientation and aspect ratio.
- **Contour Proximity and Orientation**: I calculate the slope and distance between the centroids of adjacent contours. Contours that are proximal and share a similar diagonal orientation are considered part of the same capillary, to prevent overcounting.

This method is meticulously outlined and demonstrated in the [NFC Capillaries -Sevillano.ipynb](/NFC%20Capillaries%20-Sevillano.ipynb)
 notebook, showcasing each step with corresponding code and visual outputs. Additionally, [NFC_Sevillano_KimberlyGrace_presentation.pdf](/NFC_Sevillano_KimberlyGrace_presentation.pdf) provide visual summaries and discussions of the methodology and its effectiveness.

## Objective

The primary objective is to establish a non-ML/DL reliant methodology that is robust and accurate for capillary detection and counting in varied imaging conditions. This project stands as a significant contribution to image processing in medical diagnostics, reflecting an innovative approach to traditional image analysis challenges.

## Results

The outcomes of this method are thoroughly documented in the [Poster_NFC_Sevillano.pdf](/Poster_NFC_Sevillano.pdf) , which contains a detailed account of the processes, results, and implications of the findings.

## Contents

- [NFC Capillaries -Sevillano.ipynb](/NFC%20Capillaries%20-Sevillano.ipynb) : A comprehensive Jupyter Notebook documenting the entire process of capillary detection and counting.
- [Poster_NFC_Sevillano.pdf](/Poster_NFC_Sevillano.pdf) : A summarizing poster providing an overview and key findings of the project.
- [NFC_Sevillano_KimberlyGrace_presentation.pdf](/NFC_Sevillano_KimberlyGrace_presentation.pdf) : A detailed presentation of the project's methodology and outcomes.

## Usage

The repository is structured to provide a clear understanding of the project's workflow:
1. Start with the [Poster_NFC_Sevillano.pdf](/Poster_NFC_Sevillano.pdf) and [NFC_Sevillano_KimberlyGrace_presentation.pdf](/NFC_Sevillano_KimberlyGrace_presentation.pdf) for a high-level synopsis and method explanation.
2. Explore the [NFC Capillaries -Sevillano.ipynb](/NFC%20Capillaries%20-Sevillano.ipynb) notebook for an in-depth look at the image processing techniques used and their implementation.

## Contributions

This work is a testament to the rigorous nature of the course and my dedication to the field of medical image analysis. All materials, including the code, poster, and presentation, are the result of my personal efforts and innovations in tackling the given challenge.

## Acknowledgements

I extend my heartfelt thanks to the professor Stephanie Bricq for guiding this exploration and to my peers for their constructive critiques, which have been invaluable in refining my project.
