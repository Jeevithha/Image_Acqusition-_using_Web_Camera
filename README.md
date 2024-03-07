# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video
## Software Used
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
Developed By:JEEVITHA S
Register No:21222210016

### i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("anbu.jpg",frame)
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
    cv2.imshow('lion',frame)
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
    cv2.imshow('212222240009_anbu',image)
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
    cv2.imshow('212222240009_anbu',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
````
## Output
### i) Write the frame as JPG image
![WhatsApp Image 2024-03-07 at 09 27 35_e9971fa2](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/123623197/827ae92c-0d53-411f-af9d-79e82204c597)
### ii) Display the video
![WhatsApp Image 2024-03-07 at 09 12 35_bc028bc9](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/123623197/28ef5ded-602f-4e0d-acd6-397528ede575)
### iii) Display the video by resizing the window
![WhatsApp Image 2024-03-07 at 09 27 36_4d092acb](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/123623197/16ddc3b6-af05-493f-8084-c794131c276b)
### iv) Rotate and display the video
![WhatsApp Image 2024-03-07 at 09 27 37_b6c2f684](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/123623197/082d2d76-c6bd-4205-9203-9847c6021a82)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
