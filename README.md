# EXP NO: 02 - Record-Image Acquisition Using Web Camera
## NAME : Dhanappriya S
## REG NO :212224230056
# Aim:
To acquire an image using a web camera and display the video with resizing and rotation using Python and OpenCV.

# Procedure:

1. Import the required libraries, such as OpenCV and Matplotlib.
2. Initialize the web camera using `cv2.VideoCapture(0)`.
3. Capture an image and save it as a file.
4. Read and display the captured image using Matplotlib.
5. Capture and display video frames from the web camera.
6. Resize the video frames to the required dimensions using `cv2.resize()`.
7. Rotate the video frames by 90° clockwise using `cv2.rotate()`.
8. Release the camera after completing the operations.

# Coode:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("image.jpg", frame)
cap.release()
captured_image = cv2.imread('image.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
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
# Output :
<img width="898" height="533" alt="image" src="https://github.com/user-attachments/assets/f7ca4d7c-692a-476e-a549-a0549e4fa9a9" />
<img width="887" height="502" alt="image" src="https://github.com/user-attachments/assets/d0f20d00-ddf5-438e-a9a4-ff2036455aec" />
<img width="925" height="506" alt="image" src="https://github.com/user-attachments/assets/b0382030-1baa-46bd-a62e-e9990c759850" />
<img width="935" height="517" alt="image" src="https://github.com/user-attachments/assets/eacc3bd3-d969-4e31-9a77-2735172c7173" />

# Result :
Thus the Image Acquisition Using Web Camera was verified successfully.


