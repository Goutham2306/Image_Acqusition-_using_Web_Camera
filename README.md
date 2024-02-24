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
## Step 1:
Use cv2.VideoCapture(0) to access web camera

## Step 2:
Use cv2.imread to read the video or image

## Step 3:
Use cv2.imwrite to save the image

## Step 4:
Use cv2.imshow to show the video

## Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: KANDUKURI GOUTHAM
### Register No:  212223110019
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("NewImg.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Goutham ',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
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
    cv2.imshow('Goutham',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
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
    cv2.imshow('Goutham',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![image](https://github.com/Goutham2306/Image_Acqusition-_using_Web_Camera/assets/138971154/d4ecaa87-6a74-41a2-9a06-4b9490a796ff)

### ii) Display the video

![WhatsApp Image 2024-02-24 at 22 51 58_83adc757](https://github.com/Goutham2306/Image_Acqusition-_using_Web_Camera/assets/138971154/988728d0-c8b7-46d6-8ca3-dff8a56b610c)


### iii) Display the video by resizing the window
![WhatsApp Image 2024-02-24 at 22 54 19_ce556834](https://github.com/Goutham2306/Image_Acqusition-_using_Web_Camera/assets/138971154/eb376d69-8715-4bc3-b688-981109223e86)

### iv) Rotate and display the video
![WhatsApp Image 2024-02-24 at 22 56 51_037b1172](https://github.com/Goutham2306/Image_Acqusition-_using_Web_Camera/assets/138971154/85d0c74b-525a-4c22-a508-4e5ead1d6954)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
