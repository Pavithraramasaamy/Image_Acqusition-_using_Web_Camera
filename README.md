## EX-02 Image Acqusition using Web Camera
## DATE : 24-08-2024
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window <br>
iv) Rotate and display the video

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
End the program and close the output video window by pressing 'q

## Program:
``` Python
Developed By:Pavithra R
Register No:212222230106
```
## i) Write the frame as JPG file
```py
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
cv2.imwrite("webcam_img.jpg", frame)
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```py
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('window',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```py
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
    cv2.imshow('Sample_video',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```py
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
    cv2.imshow('Rotated',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![Screenshot 2024-09-28 102601](https://github.com/user-attachments/assets/e1b8260f-b830-4d27-80f1-cc65feeac342)

### ii) Display the video

![Screenshot 2024-09-28 102318](https://github.com/user-attachments/assets/eac8be39-8dae-411b-a302-ab52695e20ec)

### iii) Display the video by resizing the window

![Screenshot 2024-09-28 102350](https://github.com/user-attachments/assets/c368570f-3a93-45bd-97cb-2b1fa8f80c54)


### iv) Rotate and display the video
![Screenshot 2024-09-28 102533](https://github.com/user-attachments/assets/49aa373b-1073-4b12-b81a-c7da2d9ddb88)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
