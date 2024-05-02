# OCR based Medical Data Extraction Project

## Problem statement

### Background:

- Health insurance companies are required by government regulations to follow specific procedures for issuing claims.
- This involves processing images of patient details and prescriptions sent by hospitals or individual doctors to extract essential data.
  
### Outsourcing Workforce:

- Many insurance companies outsource this task to companies like "Mr. X Data Analytics" to manually extract information from images.
-  Mr. X Data Analytics utilizes software where scanned images are displayed, and personnel manually type the information into the right-side column while selecting the type of data.
  
### Challenges and Solution:
- Manual extraction often leads to errors, especially when dealing with a large volume of images, such as during the pandemic.
- Additionally, insurance companies require data to be extracted within a 24-hour timeframe.
- To address these challenges, Mr. X Data Analytics is considering a software upgrade to improve efficiency and accuracy in data extraction


## Solution Approach

### Automated Data Extraction:

- Developing a program to automate the extraction of data from images aims to streamline the process and minimize manual intervention.
-  While machines cannot entirely replace human involvement, this automated system significantly reduces the time and effort required for data extraction.
  
### Utilizing Python and pytesseract Library:

- Leveraging the capabilities of Python programming language and the pytesseract library from Google, the program performs automatic data extraction from images. pytesseract enables Optical
- Character Recognition (OCR), allowing the program to interpret text from images accurately.
  
### Data Processing with Regex:

- The extracted data undergoes further processing using the Regex module to refine and distill the desired output.
-  Regex facilitates pattern matching and manipulation of textual data, ensuring the accuracy and relevance of the extracted information.
  
### Human Verification:
- Despite the automation, human verification remains crucial for ensuring data accuracy and integrity.
- A designated person reviews the extracted data to confirm its correctness before submission, maintaining quality assurance standards.


## Technologies Used
- Python
- Object-Oriented Programming (OOP)
- Pdf2image module
- OpenCV
- pytesseract
- Regular Expression (Regex)
- pytest
- Postman
- FastAPI

## Workflow

<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/workflow.jpg" class = "center">

### PDF to Image
**Library Used:** pdf2image library employed for converting PDF files to images, facilitating further data extraction.

### Without Preprocessing Data Extraction
**Approach:** Attempted data extraction from source files without any preprocessing.
**Result:** Due to the unstructured nature of the source files, the extracted data did not meet expectations, indicating the need for preprocessing before extraction.

<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/dark_image.jpg" width="350" class="center">

### Extracted data from the above image
```commandline
Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Maria Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

—momennannenncmneneunnmnnnnninsissiyoinnitnahaadaanih issn earnttneenrenen:

Prednisone 20 mg
Lialda 2.4 gram

3 days,

or 1 month
```
---

### Image Preprocessing with OpenCV

**Approach:** Decision made to preprocess images using the OpenCV module before data extraction.

**Method:** Initially applied normal thresholding to the images.

**Result:** The result of the normal thresholding process yielded the following image:

<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/filter_dark.jpg" width="350" class="center">



### Improved Approach: Adaptive Thresholding

**Problem Identification:** Normal thresholding caused fading out of areas containing shadows or noise, potentially resulting in data loss.

**Solution Exploration:** In search of a better approach, adaptive thresholding technique was considered.

**Methodology:** Adaptive thresholding involves dividing the image into sub-images, with different thresholding values applied to each sub-region.

**Result Comparison:** The end result of adaptive thresholding was found to be significantly better compared to normal thresholding, offering improved data extraction accuracy and preserving details even in areas affected by shadows or noise.

<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/adaptive_filter_dark.jpg" width="350" class='center'>


### Image Data Extraction post preprocessing

```commandline
Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Marta Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

K

Prednisone 20 mg
Lialda 2.4 gram

Directions:

Prednisone, Taper 5 mg every 3 days,
Finish in 2.5 weeks a
Lialda - take 2 pill everyday for 1 month
```
---
### Notebook

Jupyter Notebooks were utilized for incremental development of small functionalities, crucial for later integration into the class design.
[Notebooks](https://github.com/sushmitafordata/Healthcare-Project-Python/tree/main/Backend/Notebooks)

---
### OOPS design

The code was written in using OOPs concepts for extracting the medical data from prescription and patient details documents.

[Code](https://github.com/sushmitafordata/Healthcare-Project-Python/tree/main/Backend/src)

---
### Regular expression

using regular expression module we can match the patterns and extract the data we want from the files. For this project, 
analyst the medical files and as fact all the medical documents will follow same pattern, we wrote patterns that match only the required data.
Before writing the python code, It is advisable to practise and match the patterns in regex 101 website.

[regex101](https://regex101.com/)

---
### Test driven Development

In this project test driven development methodology was used to develop the code. For testing pytest module was used. 
For all the methods and final result the test cases was designed and checked simultaneously while developing the code.

[Test cases](https://github.com/sushmitafordata/Healthcare-Project-Python/tree/main/Backend/Test)

---
### FastApi

Used FastAPI for hosting the server of the project. FastApi, as name suggest is help us to develop fast and some other advantages are,

- In build Data validation
- In build Documentation
- Fast running and performance

---
### Postman

As it is a backend project, not developed frontend part. For checking how the server responds for http requests, used postman to trigger http requests and tested the outcome.

<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/postman.png" width="600" class="center">

---
## Result

This backend functionality can be integrated into the Mr.X Analytics existing software and data can be extracted automatically. 
The extracted data may have some errors, the person who is performing the work has to correct it and submit the response.

### Benefits

- Mr.X Analytics can save at least of 30 secs for each document. It is small amount of time when looking for one document, but cumulatively it can save a tremendous amount of time which can help the company to complete more documents within the given time and make more profit
- The company doesn't have to hire extra people in the season time.
- As it is a combination of automation and manual the error will be very much low.
