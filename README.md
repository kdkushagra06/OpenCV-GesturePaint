# OpenCV-GesturePaint
A real-time computer vision application that enables users to draw on a virtual canvas using hand gestures and facial cues. Built with OpenCV and MediaPipe, the system dynamically changes drawing color based on face detection, creating an intuitive, touchless interaction experience.

# OpenCV-GesturePaint - AI Powered Air Drawing with Emotion Detection

EmotionInk is a Computer Vision based touchless drawing system that allows users to draw in air using hand gestures while dynamically changing the drawing color based on facial emotion detection. The project combines Hand Tracking, Gesture Recognition, and Facial Emotion Analysis to create an interactive human-computer interaction system.

## Features

* Air Drawing using Hand Gestures
* Eraser Mode using Two-Finger Gesture
* Facial Emotion Detection (Happy / Sad / Neutral)
* Emotion-Based Color Changing Brush
* Smooth Drawing using Deque Smoothing Algorithm
* Real-Time Canvas Overlay
* Custom Hand Skeleton Visualization
* Eraser Icon Overlay
* Optimized for Real-Time Performance

## Technologies Used

* Python
* OpenCV
* MediaPipe
* NumPy
* Computer Vision
* Machine Learning (Landmark-Based Emotion Detection)

## System Workflow

1. Webcam captures live video.
2. MediaPipe detects hand landmarks.
3. Index finger tip is used as drawing pointer.
4. Deque smoothing algorithm reduces hand jitter.
5. Face Mesh detects facial landmarks.
6. Mouth landmarks are used to detect emotion.
7. Brush color changes based on detected emotion.
8. Canvas is merged with webcam feed using bitwise masking.

## Controls

| Gesture                  | Action |
| ------------------------ | ------ |
| Index Finger Up          | Draw   |
| Index + Middle Finger Up | Erase  |
| Press X                  | Exit   |

## Future Improvements

* Add more emotions (Angry, Surprise)
* Add color selection gestures
* Add shape drawing mode
* Add save canvas feature
* Add virtual mouse mode
* Build GUI buttons

## Author

Kushagra Divya
AI | Computer Vision | OpenCV | MediaPipe
