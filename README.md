# Amazon ML CHallenge 2024

## Overview
This project was developed as a solution for the Amazon ML Challenge 2024, which aimed to extract measurement units (e.g., kg, cm) from product images using Optical Character Recognition (OCR) with the help of the PyTesseract library. The model was developed by a team consisting of Nikhil, Ashish, Ayush, and myself. The extraction process involves downloading images, processing them, and applying OCR to retrieve the text data.

## Key Processes
- Image Text Extraction: The extract_text_from_image function downloads an image from a given URL and extracts text using PyTesseract.
- Parallel Image Processing: The process_images function processes multiple images in parallel using the ProcessPoolExecutor from the concurrent.futures library to optimize performance.
- Regular Expression Patterns: Regular expression patterns are defined for different measurement units in the unit_patterns dictionary
- Unit Extraction by Entity: The extract_units_by_entity function extracts units based on the predefined regular expression patterns
- Unit Normalization: The normalize_units function normalizes extracted units by replacing abbreviations with full unit names using a predefined unit_mapping dictionary
- Comparison and Filtering: The compare_units function compares extracted units with entity values and filters rows where units are successfully extracted

## Technologies Used
- Python: The programming language used for the implementation.
- PyTesseract: A Python wrapper for Google's Tesseract-OCR Engine, used for extracting text from images.
- OpenCV: A popular computer vision library, used in conjunction with PyTesseract for image processing tasks.
- Pandas: A data manipulation and analysis library, used for working with tabular data.
- Regular Expressions: Used for defining patterns to extract specific units from the extracted text.
- Concurrent Processing: Utilized the concurrent.futures library for parallel processing of images to improve performance

  ## Implementation details
- Image Text Extraction: The extract_text_from_image function downloads an image from a given URL using the requests library and extracts text using PyTesseract.
- Parallel Processing: The process_images function processes multiple images in parallel using the ProcessPoolExecutor from the concurrent.futures library. It submits each image URL to the executor and collects the results.
- Unit Extraction: Regular expression patterns are defined in the unit_patterns dictionary for different measurement units. The extract_units_by_entity function applies these patterns to the extracted text to find matches

![image](https://github.com/user-attachments/assets/89066994-907c-4c3e-aa27-76d9fe79d867)

  
- Unit Normalization: The normalize_units function normalizes the extracted units by replacing abbreviations with full unit names using the unit_mapping dictionary3
- Comparison and Filtering: The compare_units function compares the normalized extracted units with the entity values. Rows where units are successfully extracted are filtered for further processing3

![image](https://github.com/user-attachments/assets/88f94f3f-5506-4523-b845-b0e8b4f0dc35)


- Saving Results: The filtered DataFrame with extracted units is saved to a CSV file named dummy_train_with_units.csv.

  ![image](https://github.com/user-attachments/assets/cdbd7c4c-80c9-42c5-ab60-d395eb758cfe)


  
