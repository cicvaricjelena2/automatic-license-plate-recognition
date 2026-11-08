# Automatic License Plate Recognition (ALPR)

An image processing and optical character recognition project for automatic vehicle license plate detection and recognition using Python, OpenCV, and Tesseract OCR.

The system processes vehicle images, detects potential license plate regions, extracts the plate, and recognizes its alphanumeric characters.

Project Overview

The implementation consists of several processing stages.

1. Image Loading

* Loading vehicle images from a local image dataset.
* Supporting JPG, JPEG, PNG, BMP, and WEBP formats.
* Image preprocessing using OpenCV.

2. License Plate Detection

Potential license plate regions are detected using a combination of image processing techniques:

* Grayscale conversion.
* Bilateral filtering.
* Canny edge detection.
* Image dilation.
* Contour detection.
* Polygon approximation.
* Geometric filtering based on aspect ratio and area.
* Sobel-based fallback detection.

Candidate regions are ranked using geometric and edge-based criteria.

3. Image Preprocessing

After detecting a candidate plate region, the system performs:

* Bounding box extraction.
* Cropping with padding.
* Grayscale conversion.
* Removal of unnecessary margins.
* Image resizing.
* Gaussian blurring.

4. Image Binarization

Multiple binarization techniques are evaluated to improve OCR performance:

* Adaptive Gaussian Thresholding.
* Otsu Thresholding.
* Inverted binary images.
* Morphological opening and closing.

5. Optical Character Recognition

Tesseract OCR is used to extract alphanumeric characters from the processed plate image.

The implementation evaluates multiple OCR configurations using different page segmentation modes and selects the candidate with the highest recognition score.

6. Post-processing and Plate Normalization

The recognized text is cleaned and normalized using character mapping rules.

The implementation addresses common OCR confusions, such as:

* O and 0
* I and 1
* Z and 2
* S and 5
* B and 8
* G and 6

Regular expressions are used to recognize supported Serbian and Bosnian license plate formats.

Technologies

* Python
* OpenCV
* NumPy
* Matplotlib
* Tesseract OCR
* Pytesseract
* Image Processing
* Optical Character Recognition (OCR)

Repository Structure

automatic-license-plate-recognition/
│
├── notebooks/
│   └── license_plate_recognition.ipynb
│── photos/
├── README.md
├── requirements.txt
└── .gitignore

Requirements

* Python 3.x
* OpenCV
* NumPy
* Matplotlib
* Pytesseract
* Jupyter Notebook
* Tesseract OCR executable

Tesseract OCR must be installed separately and accessible through the system PATH.

How to Run

Clone the repository:

git clone https://github.com/cicvaricjelena2/automatic-license-plate-recognition.git

Install the Python dependencies:

pip install -r requirements.txt

Install Tesseract OCR separately and configure its executable path if necessary.

Place the input images in a directory named baza in the project root.

Open Jupyter Notebook:

jupyter notebook

Open license_plate_recognition.ipynb and execute the cells.

Notes

The notebook currently demonstrates the detection and recognition pipeline on individual input images.

The image dataset is expected to be provided locally in the baza/ directory and is not included in this repository.

Recognition performance depends on image quality, plate visibility, lighting conditions, viewing angle, and OCR accuracy.

Conclusion

This project demonstrates a complete image processing and OCR pipeline for automatic license plate recognition, combining geometric candidate detection, image enhancement, text extraction, and format-aware post-processing.
