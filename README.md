# Real-Time-Sudoku-Solver
## OVERVIEW: 
Sudoku is one of the most popular puzzle of all time.The goal of Sudoku is to fill 9x9 grid such that each row,each column and 3x3 grid contains all of the digits between 1 to 9.
In this project we aim to create a real time Sudoku solver  which recognise the elements of Sudoku puzzle and providing a digital solution using Computer vision.
Sudoku Solver is the collection of very basic image processing techniques. A very good way to start is the OpenCV library which can be compiled on almost all the platforms. 

## PRE-REQUISITES FOR THE PROJECT:

#### Python programming language
Basic knowledge of coding and syntax formats of python is essential for this project. Python is advantageous as it easy to comprehend and consists of large number of inbult libraries that facilitate faster outputs. python can be learned through tutorials on [python.org](https://www.python.org/about/gettingstarted/) and vieos available online
#### OpenCV library
Basic knowledge of opencv regarding use applications and syntax are essential here. It is a library in python that helps with computer vision and is more convenient as it provides large number of functions for conversions and processing. It can be learned on [opencv.org](https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_tutorials.html).
#### Numpy library
Basic knowledge of numpy including syntax and computational part are essentail to form image arrays. It is a lirary in pyton used to perform mathematical computation. it can be learned from [numpy.org](http://www.numpy.org/).
#### Tersseract with python
This is also known as pytersseract and is used for object recognition. Python-tesseract is an optical character recognition (OCR) tool for python. That is, it will recognize and "read" the text embedded in images. It can be learned from [pype.org](https://pypi.org/project/pytesseract/). 

## COMPUTER VISION:
Computer vision is an interdisciplinary field that deals with how computers can be made for gaining high-level understanding from digital images or videos. From the perspective of engineering, it seeks to automate tasks that the human visual system can do. Computer vision is concerned with the theory behind artificial systems that extract information from images.Computer vision is useful to emulate human vision like object recognition, defect detection or automatic driving etc.

## CASE STUDY:

### Backtracking Algorithm: 
Backtracking is a general algorithm for finding all (or some) solutions to some computational problems, notably constraint satisfaction problems, that incrementally builds candidates to the solutions, and abandons a candidate ("backtracks") as soon as it determines that the candidate cannot possibly be completed to a valid solution.
This includes a recursive function call.

### Image Processing:
#### Digital Image: 
A digital image is a numeric representation, normally binary, of a two-dimensional image. Depending on whether the image resolution is fixed, it may be of vector or raster type. By itself, the term "digital image" usually refers to raster images or bitmapped images (as opposed to vector images).

 Real-Time-Sudoku-Solver/webcam.png Types of digital image
- Binary Image
- Grayscale Image
- RGB Image
- HSV Image
#### Image Thresholding: 
Thresholding is the simplest method of image segmentation. From a grayscale image, thresholding can be used to create binary images.

Types of threshoding:
- Simple thresholding
- Ostu's Binarization
- Adaptive Thresholding
#### Cotours:
Contours can be explained simply as a curve joining all the continuous points (along the boundary), having same color or intensity. The contours are a useful tool for shape analysis and object detection and recognition.
- For better accuracy, use binary images. So before finding contours, apply threshold or canny edge detection.
- findContours function modifies the source image. So if you want source image even after finding contours, already store it to some other variables.
 - In OpenCV, finding contours is like finding white object from black background. So remember, object to be found should be white and background should be black.
 
### Optical character recognition:
Optical character recognition (also optical character reader, OCR) is the mechanical or electronic conversion of images of typed, handwritten or printed text into machine-encoded text, whether from a scanned document, a photo of a document, a scene-photo (for example the text on signs and billboards in a landscape photo) or from subtitle text superimposed on an image (for example from a television broadcast)

We have used OCR for image recognition through pytesseract interface. 

##  SOLVER (THE CODE)

#### 1.Importing Libraries:
To begin with the solver's code we will have to import the following inbuilt libraries in python.
Note: just pip install them in case if terminal throws error
![alt import](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/import.png "To include libraries")

#### 2.Acquiring image:
To acquire the image we used video form in Opencv and 'cv2.VideoCapture(time_in_milliseconds)' is the command that we used for the same.
For grid detection we have used contours. The four corners of the grid are evaluated and the sudoku grid is then reoriented with the help of following command line.
![alt webcam](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/webcam.png "To get image of grid")

#### 3.Getting clear digits and removing noise:
We have used contours to get image of cells of grid that conatin digits. also the digits are made more clear and sharp by eroding. noise is also reduced bt filling the digits ie. by 'cv2.threshold()'.
![alt contours](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/contours.png "to reduce noise")

#### 4.Recognising the value of digits by sending it to OCR:
Pytesseract is used for optocal character recognition here and then it is further processed. The pytesseract convers the value of recognised digit to a string that can we used for further operations. The output of pytesseract is quite accurate. the code that we used is:
![alt pytesseract](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/ocr.png "for digit recognition")

#### 5.SOLVER CODE AND MECHANISM:
###### (a). Checking usasigned cells and digits thwt are sent by the main solver function.
The following program was used to chek the empty cells and weather a particular digit was present in the row/column/3x3 grid. It was basic 2-Dimensional array analysis.
![alt check](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/check.png "check")

###### (b). Backtracking function:
The solver uses recursive function call to check digits values. It also then changes the digits in case if the digit is already present in the grid.
![alt backtrack](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/solver.png "slover")

#### 6. Displaying Output:
The program then comiles the array and displays the output on the screen along with existing image of the sudoku grid. It also displays the solved grid on the screen.
![alt output](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/print_output.png "output")

## REFERENCES
- Python [python.org](https://www.python.org/doc/)
- OpenCV tutorials [opencv tutorials](opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py.../py_intro.html)
- Stackerflow [for doubts](https://stackoverflow.com/)

## Our final program is attached here:
[PROJECT](https://github.com/AyushiTiwari/Real-Time-Sudoku-Solver/blob/master/project.py)

### OUR MENTORS:-
- Aman Jain
- Akshay Kulkarni
- Navid Panchi
- Amit Balgi

### OUR TEAM :-
- Siddharth Gupta
- Abhijit Adsul
- Nikhil Dhoot
- Ayushi Tiwari
