# EXP-2-Record-Image-Acquisition-using-Web-Camera
# Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file Display the video Display the video by resizing the window Rotate and display the video

# 🛠️ Software Used
Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2)

# ⚙️ Algorithm
Step 1: Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2: Capture frames continuously from the webcam.

Step 3: Save a frame as a JPG image using cv2.imwrite().

Step 4: Display the live video stream using cv2.imshow().

Step 5: Resize the frame and rotate it using OpenCV functions, then display the processed frames.

# 💻 Program
Developed By: Name: Lokesh M

Register No:212224230142

# Output

i) Write the frame as JPG image Captured image is saved as captured_image.jpg
```

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

```
<img width="1137" height="938" alt="Screenshot 2026-07-29 230433" src="https://github.com/user-attachments/assets/de6efabf-a82c-4a8a-89a4-a46b63390835" />

ii) Display the video Live webcam video is displayed

```
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

```
<img width="1072" height="830" alt="Screenshot 2026-07-29 230441" src="https://github.com/user-attachments/assets/4a677949-c24f-4da3-b0e3-6662a9c3ab7e" />

iii) Display the video by resizing the window

```
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

```
<img width="1125" height="882" alt="Screenshot 2026-07-29 230449" src="https://github.com/user-attachments/assets/dadd8244-7084-4379-afb6-007bc261edd0" />


 iv) Rotate and display the video

 ```
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
<img width="1088" height="870" alt="Screenshot 2026-07-29 230457" src="https://github.com/user-attachments/assets/85938fe0-2dcb-4c97-a01f-f17d2d5802ef" />


# Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.





