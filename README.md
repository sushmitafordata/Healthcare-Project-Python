# OCR based Medical Data Project in Python

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

#### **Pattern Matching with Regular Expression**
**Approach:** Utilized the Regular Expression (regex) module to match patterns and extract required data from medical files.
**Pattern Consistency:** Due to the standardized format of medical documents, consistent patterns were identified for data extraction.
**Preparation:** Prior to writing Python code, practiced and validated patterns using the regex 101 website.
Efficiency Enhancement: Pattern matching ensures extraction of only the necessary data, optimizing the processing of medical documents.

[regex101](https://regex101.com/)

---

### Test-Driven Development with Pytest
**Methodology:** Adopted test-driven development (TDD) approach throughout the code development process.
**Testing Framework:** Utilized the pytest module for writing and executing test cases.
**Simultaneous Testing:** Test cases for all methods and final results were designed and checked simultaneously during code development.
**Benefits:** Ensured code functionality and integrity at each stage of development, promoting robustness and reliability in the final implementation.

[Test cases](https://github.com/sushmitafordata/Healthcare-Project-Python/tree/main/Backend/Test)

---

#### Utilization of FastAPI for Server Hosting
**Framework Selection:** FastAPI was chosen for hosting the project server due to its speed and efficiency.
Advantages:
**In-built Data Validation:** FastAPI provides built-in data validation, ensuring the integrity of incoming requests.
**In-built Documentation:** Automatic generation of API documentation by FastAPI streamlines the development and maintenance process.
**Performance:** FastAPI is known for its fast runtime performance, contributing to improved server responsiveness and scalability.

---

### Testing with Postman
**Backend Focus:** Since the project is backend-oriented, no frontend development was undertaken.
**Testing Tool:** Postman was employed to trigger HTTP requests and assess server responses.
**Purpose:** Postman facilitated thorough testing of the server's functionality and ensured proper handling of HTTP requests and responses.
**Efficiency:** Utilizing Postman streamlined the testing process, allowing for comprehensive validation of the backend implementation.
<img src="https://github.com/Naveen-S6/Data_Extraction_Healthcare_Project/blob/main/Backend/Notebooks/postman.png" width="600" class="center">

---
### Result
- The backend functionality developed can seamlessly integrate into Mr.X Analytics' existing software, enabling automatic data extraction from documents. - - However, manual verification and correction of extracted data are necessary before submission.

### Benefits
- **Time Saving:** Mr.X Analytics stands to save a significant amount of time, approximately 30 seconds per document, ultimately leading to increased productivity and profitability.
- **Seasonal Staffing:** Eliminates the need for hiring additional personnel during peak seasons, ensuring operational efficiency and cost savings.
- **Error Reduction:** Combining automation with manual verification results in a substantial decrease in errors, enhancing data accuracy and reliability.
