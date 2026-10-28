# Webcam Image Capture and Video Processing Using OpenCV

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file
2. Display the video
3. Display the video by resizing the window
4. Rotate and display the video

---

## 🛠️ Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)

---

## ⚙️ Algorithm

### Step 1:

Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:

Capture frames continuously from the webcam.

### Step 3:

Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:

Display the live video stream using `cv2.imshow()`.

### Step 5:

Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

```python
import cv2

# Initialize the webcam
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Error: Cannot access webcam")
    exit()

# Capture and save one frame as JPG
ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Image saved as captured_image.jpg")

while ret:
    # Display original video
    cv2.imshow("Webcam Video", frame)

    # Resize and display video
    resized_frame = cv2.resize(frame, (640, 480))
    cv2.imshow("Resized Video", resized_frame)

    # Rotate and display video (90 degrees clockwise)
    rotated_frame = cv2.rotate(
        frame, cv2.ROTATE_90_CLOCKWISE
    )
    cv2.imshow("Rotated Video", rotated_frame)

    # Exit when 'q' is pressed
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

    ret, frame = cap.read()

cap.release()
cv2.destroyAllWindows()
```

### Developed By:

**Name:** Shaajini N

### Register No: 212225040395

---

## Output

### i) Write the frame as JPG image

Captured image is saved as `captured_image.jpg`.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/21f3f8f4-263d-482c-8973-75f8594e5ea1" />

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/ed004ac1-281e-41d1-a0e5-f6a4d90fc9dd" />

### ii) Display the video

Live webcam video is displayed.

<img width="1917" height="1073" alt="image" src="https://github.com/user-attachments/assets/1c610a34-0b50-4240-9b94-771b43f178bf" />


### iii) Display the video by resizing the window

Video is shown in resized resolution (640 × 480).

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/f2247640-8bb7-4dfe-8e0c-ba03ad5edf9b" />


### iv) Rotate and display the video

Video is displayed after rotation (90° clockwise).

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/850d0806-c14e-4825-860b-0930e5fbbc75" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
