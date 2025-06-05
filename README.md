# hand-gesture-tracker
Overview
This project implements a gesture control system using computer vision and machine learning. It leverages MediaPipe for hand tracking and gesture recognition to control various system functions like cursor movement, clicking, scrolling, volume adjustment, and brightness control - all through hand gestures captured by a webcam.

Key Features
🖱️ Cursor Control: Move mouse pointer with a V-gesture

🖱️ Click Operations:

Single click (MID gesture)

Double click (TWO_FINGER_CLOSED gesture)

Right click (INDEX gesture)

📊 Scrolling: Vertical and horizontal scrolling with pinch gestures

🔊 Volume Control: Adjust system volume with major hand pinch

💡 Brightness Control: Adjust screen brightness with major hand pinch

🤚 Multi-hand Recognition: Supports both left and right hands

🔄 Gesture Stabilization: Noise reduction for reliable gesture recognition

Gesture Mappings
Gesture	Action
✌️ V_GEST	Mouse movement
✊ FIST	Mouse drag (hold left button)
🖕 MID	Left click
☝️ INDEX	Right click
🤏 PINCH_MINOR (minor hand)	Scrolling
🤏 PINCH_MAJOR (major hand)	Volume/Brightness control
🤘 TWO_FINGER_CLOSED	Double click
🖐️ PALM	No action
Requirements
Python 3.7+

OpenCV

MediaPipe

PyAutoGUI

pycaw (for volume control)

screen-brightness-control

Protobuf

NumPy

Installation
bash
# Install required packages
pip install opencv-python mediapipe pyautogui pycaw screen-brightness-control protobuf numpy

# (Optional) For better performance with GPU support
pip install tensorflow-gpu
Usage
Run the script:

bash
python gesture_controller.py
Position your hands in front of the webcam

Use the following gestures to control your system:

Make a ✌️ "V" gesture to move cursor

Make a ✊ fist to drag items

Pinch with your dominant hand for volume/brightness

Pinch with your non-dominant hand for scrolling

Use 🖕 middle finger for left click

Use ☝️ index finger for right click

System Architecture
GestureController (Main)
├── HandRecog (Gesture Recognition)
│   ├── Landmark processing
│   ├── Gesture classification
│   └── State management
└── Controller (System Control)
    ├── Cursor movement
    ├── Click handling
    ├── Volume control
    └── Brightness control
Configuration
Adjust pinch_threshold in Controller class for sensitivity

Modify dom_hand in GestureController for left-handed mode

Change camera index in GestureController.cap for different cameras

Performance Notes
Works best in well-lit environments

Requires consistent webcam feed at 30+ FPS

For better performance:

Use a GPU-enabled environment

Reduce camera resolution if experiencing lag

Ensure hands are clearly visible without obstructions

Troubleshooting
Problem: Gestures not recognized consistently

Solution: Ensure proper lighting and clean background

Problem: Volume/Brightness not changing

Solution: Check system permissions for audio/brightness control

Problem: High CPU usage

Solution: Reduce camera resolution in cv2.VideoCapture(0) parameters

Future Improvements
Add gesture customization interface

Implement gesture training module

Add support for multi-monitor setups

Develop game control profiles

Create virtual keyboard integration

License
This project is available under the MIT License. See LICENSE file for details.

