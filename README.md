# EX 02: Image_Acqusition-_using_Web_Camera
## NAME:vignesh R
## REG NO:212223240177
## Date No:
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.
### Step 2:
Use cv2.imread to read the video or image.
### Step 3:
Use cv2.imwrite to save the image.
### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
``` Python
### Developed By:vignesh R
### Register No:212223240177

## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
## ii) Display the video
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
## iii) Display the video by resizing the window
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
## iv) Rotate and display the video
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
```
## Output

### i) Write the frame as JPG image
<img width="604" height="438" alt="image" src="https://github.com/user-attachments/assets/97fdafea-2813-4d92-8dbf-42b63efb8599" />

### ii) Display the video
<img width="549" height="406" alt="image" src="https://github.com/user-attachments/assets/5984df6e-27c7-4fa3-8ee0-49b9ebcf5a8c" />

### iii) Display the video by resizing the window
<img width="308" height="423" alt="image" src="https://github.com/user-attachments/assets/217033ae-48ce-4c0b-8fd3-0a48a7636a2f" />

### iv) Rotate and display the video
<img width="345" height="402" alt="image" src="https://github.com/user-attachments/assets/d7a8b804-4b22-49ae-9064-5f16d9d90d9a" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
