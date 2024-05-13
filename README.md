# Image_Acqusition-_using_Web_Camera
### Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

### Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
### Step 2:
Use cv2.imread to read the video or image
### Step 3:
Use cv2.imwrite to save the image
### Step 4:
Use cv2.imshow to show the video
### Step 5:
End the program and close the output video window by pressing 'q'

## Program:
### Developed By:JEEVITHA S
### Register No:212222100016
## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("praga.jpg",frame)
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
    cv2.imshow('212222110033_praga',image)
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
    cv2.imshow('212222110033_praga',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![WhatsApp Image 2024-03-07 at 09 09 58_8f89d6e6](https://github.com/pragachellapillai/Image_Acqusition-_using_Web_Camera/assets/148254952/62ecbcb4-de26-4088-b0f3-143ea1ab3e14)
### ii) Display the video
![WhatsApp Image 2024-03-07 at 09 02 45_ad0b22ab](https://github.com/pragachellapillai/Image_Acqusition-_using_Web_Camera/assets/148254952/c622381b-4082-4881-8a80-308b482e0589)
### iii) Display the video by resizing the window
![WhatsApp Image 2024-03-07 at 09 07 30_124b46ac](https://github.com/pragachellapillai/Image_Acqusition-_using_Web_Camera/assets/148254952/fcf504ad-0a39-4963-bb9e-0507a2861a54)
### iv) Rotate and display the video
![WhatsApp Image 2024-03-07 at 09 07 30_e641769f](https://github.com/pragachellapillai/Image_Acqusition-_using_Web_Camera/assets/148254952/55bdebf9-ceb0-47d8-98bd-ea3c567da5c4)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
