Handwritten Text Recognition and Evaluation Tool
Overview
This CLI tool leverages Tesseract OCR to recognize handwritten text from answer sheets. The extracted text is then processed using Natural Language Processing (NLP) techniques to evaluate the answers and assign marks. The tool is designed to automate the grading process for handwritten exams or assignments.

Installation
Tesseract-OCR Engine
Install Tesseract-OCR by following the instructions provided in the Tesseract GitHub repository.
Python Dependencies
Install the required Python dependencies using pip:

bash
Copy code
pip install pytesseract pillow pandas numpy matplotlib
Usage
1. Clone the Repository
Clone this repository into your working directory:

bash
Copy code
git clone https://github.com/yourusername/yourrepository.git
cd yourrepository
2. Configure Tesseract Path
Update the path of the Tesseract executable in main.py to match your installation. Locate the following line in main.py and modify it accordingly:

python
Copy code
pytesseract.pytesseract.tesseract_cmd = r'/path/to/tesseract'
3. Add Image for Testing
Place the image of the answer sheet you wish to test into the images folder within the repository.

4. Run OCR
Execute the following command to perform OCR on the image:

bash
Copy code
python main.py imagename
This will generate a HOCR file, which is an XHTML-like format containing the recognized text.

5. Convert HOCR to DataFrame
To convert the HOCR file into a DataFrame and store the results in a pickle or JSON file, run:

bash
Copy code
python file_conversion.py hocrfilename
This script will process the HOCR file and save the structured data in the specified format.

Phases
Phase 1: OCR and JSON Conversion
This phase demonstrates the OCR functionality and converts the recognized text into a JSON format. The output JSON file contains structured data extracted from the handwritten text.

Phase 2: NLP-Based Answer Evaluation
In this phase, we use the Natural Language Toolkit (nltk) to create an NLP model that evaluates the quality of the answers. This involves processing the extracted text to assess and score the responses based on predefined criteria.

Future Work
Improve OCR accuracy for diverse handwriting styles.
Enhance the NLP model for more sophisticated answer evaluation.
Integrate the tool with a web interface for user-friendly interaction.