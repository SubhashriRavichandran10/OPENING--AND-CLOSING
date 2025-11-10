# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:



Import required libraries.

### Step2:
Create white noise image and use it to display the opening image.

### Step3:

Display the opening image.
### Step4:

Create black noise image and use it to display the closing image



 
## Program:

``` Python
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline


# Create the Text using cv2.putText

def load_img():
    blank_img =np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='ABCDE',org=(50,300), fontFace=font,fontScale= 5,color=(255,255,255),thickness=25,lineType=cv2.LINE_AA)
    return blank_img

# Create the structuring element

def display_img(img):
    fig = plt.figure(figsize=(12,10))
    ax = fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()

# Use Opening operation
white_noise = np.random.randint(low=0,high=2,size=(600,600))
white_noise
white_noise = white_noise*255
white_noise # Display
noise_img = white_noise+img
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
# Use Closing Operation
img = load_img()
black_noise = np.random.randint(low=0,high=2,size=(600,600))
black_noise
black_noise= black_noise * -255
black_noise_img = img + black_noise
black_noise_img     # display
black_noise_img[black_noise_img==-255] = 0
closing = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing)








```
## Output:

### Display the input Image

<img width="656" height="648" alt="image" src="https://github.com/user-attachments/assets/f90c6aa0-aff1-4081-bbf7-54e79d4eb09d" />


### Display the result of Opening

<img width="650" height="649" alt="image" src="https://github.com/user-attachments/assets/2e5867d3-ac01-462a-bae2-9d28ab30e6fd" />


### Display the result of Closing


<img width="647" height="642" alt="image" src="https://github.com/user-attachments/assets/98a1b89c-ef61-4b7c-99dd-38f73b850339" />

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
