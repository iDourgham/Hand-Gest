# Hand Gesture Classification Using MediaPipe

## Overview
This project focuses on extracting hand landmarks using **MediaPipe** from the **HaGRID dataset** to develop a hand gesture classification system.

## Progress Overview

### 1. **Initializing MediaPipe**
- Implemented **MediaPipe Hands** for detecting and tracking hand landmarks.
- Utilized:
  ```python
  mp_drawing = mp.solutions.drawing_utils # Helps visualize hand landmarks
  mp_hands = mp.solutions.hands
  ```

### 2. **Initializing Webcam Feed**
- Set up OpenCV to capture real-time video feed:
  ```python
  cap = cv2.VideoCapture(0)  # Captures webcam feed
  ```

### 3. **Detection and Tracking Thresholds**
- Configured:
  - **Detection Confidence**: `0.8` (Threshold for initial hand detection)
  - **Tracking Confidence**: `0.5` (Threshold for continuous tracking)
  ```python
  with mp_hands.Hands(min_detection_confidence=0.8, min_tracking_confidence=0.5) as hands:
  ```

### 4. **Processing Video Feed**
- Converted each video frame from **BGR to RGB** (MediaPipe requires RGB format):
  ```python
  image = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
  ```
- Processed the frame using MediaPipe Hands:
  ```python
  results = hands.process(image)
  ```
- Converted back to **BGR** for OpenCV display:
  ```python
  image = cv2.cvtColor(image, cv2.COLOR_RGB2BGR)
  ```

### 5. **Rendering Hand Landmarks**
- Checked if hands were detected:
  ```python
  if results.multi_hand_landmarks:
  ```
- Drew hand landmarks on the video feed:
  ```python
  for num, hand in enumerate(results.multi_hand_landmarks):
      mp_drawing.draw_landmarks(image, hand, mp_hands.HAND_CONNECTIONS)
  ```

### 6. **Displaying the Video Feed**
- Used OpenCV to show the processed frames with hand landmarks:
  ```python
  cv2.imshow('Hand Tracking', image)
  ```
- Allowed exiting the application by pressing **'q'**:
  ```python
  if cv2.waitKey(10) & 0xFF == ord('q'):
      break
  ```

### 7. **Cleanup**
- Released webcam and closed all OpenCV windows:
  ```python
  cap.release()
  cv2.destroyAllWindows()
  ```

## Next Steps
- **Improve gesture classification** by training a model using extracted landmarks.
- **Enhance real-time performance** by optimizing processing speed.
- **Explore multi-hand detection** for recognizing gestures with both hands.

---
This project is a work in progress 🚀. Stay tuned for updates!

