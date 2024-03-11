# Image_Acqusition-_using_Web_Camera
## Aim
Aim:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
### Step 2:
Use cv2.imread to read the video or imag
### Step 3:
Use cv2.imwrite to save the image
### Step 4:
Use cv2.imshow to show the video
### Step 5:
End the program and close the output video window by pressing 'q'

## Program:
### Developed By:jeevitha s
### Register No:212222100016

### i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("jeevi.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
### ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('cat',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
### iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222100016_jeevi',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
### iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222100016_jeevi',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![Untitled](https://github.com/Jeevithha/Image_Acqusition-_using_Web_Camera/assets/123623197/67735d3e-5b82-4097-9901-f1d9a99c2c5e)
### ii) Display the video
![Untitled](https://github.com/Jeevithha/Image_Acqusition-_using_Web_Camera/assets/123623197/5c3c2d4f-2933-4e9e-8962-d3bb3f086d1e)
### iii) Display the video by resizing the window
![Untitled](https://github.com/Jeevithha/Image_Acqusition-_using_Web_Camera/assets/123623197/ad6991ae-8933-4411-8a84-ba6e60868045)
### iv) Rotate and display the video
![Untitled](https://github.com/Jeevithha/Image_Acqusition-_using_Web_Camera/assets/123623197/1d390733-2dcf-483b-a134-206815cc361c)

## Result:
Thus the image is accessed from webcamera and displayed using openCV
