# OpenCV-GesturePaint
A real-time computer vision application that enables users to draw on a virtual canvas using hand gestures and facial cues. Built with OpenCV and MediaPipe, the system dynamically changes drawing color based on face detection, creating an intuitive, touchless interaction experience.

# 🖌️ OpenCV-GesturePaint (Air Drawing with Emotion Control)

A real-time computer vision system that enables **touchless drawing using hand gestures**, enhanced with **facial expression–based color control** and **smoothed motion tracking**.

This project integrates **MediaPipe Hand Tracking + Face Mesh + OpenCV rendering**, along with **temporal smoothing and gesture logic** to create a stable and responsive drawing experience. 

---

##  Key Features

###  Gesture-Based Drawing

* Draw in air using your **index finger**
* Fully touchless interaction via webcam

###  Emotion-Based Color Switching

* Detects facial expression using face landmarks
* Automatically changes drawing color:

  * Happy → Green
  * Sad → Red
  * Neutral → Default

###  Smart Eraser Mode

* Activate using **index + middle finger**
* Uses thicker stroke to erase
* Displays **eraser icon overlay on fingertip**

###  Advanced Smoothing (Important)

* Uses `deque` buffer for **temporal smoothing**
* Applies **moving average filtering**:

  ```python
  points = deque(maxlen=7)
  avg_x = mean(x_points)
  avg_y = mean(y_points)
  ```
* Significantly reduces jitter and noisy tracking

###  Optimized Rendering Pipeline

* Separate canvas layer
* Efficient merging using:

  * Bitwise masking
  * Foreground-background blending

---

## Tech Stack

* **OpenCV** → Image processing & rendering
* **MediaPipe** → Hand tracking + Face mesh
* **NumPy** → Numerical operations
* **Deque (collections)** → Temporal smoothing

---

##  System Architecture

### 1. Face Analysis → Emotion Detection

* Extract facial landmarks using MediaPipe FaceMesh
* Compute:

  * Lip distance → Smile detection
  * Mouth width → Expression classification
* Maintain **emotion buffer (deque)** for stability
* Final emotion = most frequent value

---

### 2. Hand Tracking → Gesture Control

* Track **index fingertip (landmark 8)**
* Gesture logic:

  * Index up → Draw
  * Index + Middle up → Erase
  * No hand → Reset tracking

---

### 3. Motion Smoothing

* Store last N positions using deque
* Apply **moving average** to compute stable coordinates
* Eliminates high-frequency noise

---

### 4. Drawing Engine

* Draw lines between previous and current smoothed points
* Uses:

  * Anti-aliased lines for drawing
  * Thick strokes for erasing

---

### 5. Canvas Composition

* Maintain separate canvas
* Merge with live frame using:

  * Thresholding
  * Bitwise operations

---

##  Installation

```bash
pip install opencv-python mediapipe numpy
```

---

##  Run the Project

```bash
python your_script_name.py
```

Press **`x`** to exit.

---

##  Controls

| Gesture              | Action         |
| -------------------- | -------------- |
|  Index finger up   | Draw           |
|  Index + Middle up | Erase          |
|  No hand            | Reset tracking |

---

##  Demo

>  Add a GIF/video here — this is critical for showcasing the project.

---

##  Limitations

* Emotion detection is **rule-based (not ML model)**
* Performance depends on lighting and camera quality
* Single-hand tracking only

---

##  Future Improvements

* Deep learning–based emotion classification
* Multi-color gesture palette
* Shape recognition (circle, rectangle, etc.)
* Save/export drawings
* Multi-hand support
* Kalman filter for advanced smoothing

---

##  What This Project Demonstrates

* Real-time computer vision pipeline design
* Gesture recognition system
* Signal smoothing using data structures
* Human-computer interaction without hardware

---

##  Author

*Kushagra Divya
AI | Computer Vision | OpenCV | MediaPipe

---

