# Drowsiness Detection System using IBM Watson IoT
This repository contains Python code for a drowsiness detection system that uses computer vision techniques to monitor a person's eyes and detect signs of drowsiness. When drowsiness is detected, an alert is sent to the IBM Watson Internet of Things (IoT) platform, and an alarm sound is played.

## Prerequisites
Before running the code, make sure you have the following libraries and components installed:

- OpenCV
- dlib
- NumPy
- IBM Watson IoT Python SDK (ibmiotf)
- pygame
  
- You can install these dependencies using `pip`

## Setup IBM Watson IoT
Sign up for an IBM Watson IoT Platform account if you don't already have one.

Create a new device type and register a device. Note down the organization, device type, device ID, authentication method (token), and authentication token.

Replace the following variables in the code with your IBM Watson IoT credentials:

`organization`
`deviceType`
`deviceId`
`authMethod`
`authToken`

## Running the Code
1. Download the pre-trained shape predictor model from the dlib website and save it as "shape_predictor_68_face_landmarks.dat" in the same directory as the code.

2. Make sure you have an MP3 file containing the alarm sound (e.g., "oversimplified-alarm-clock-113180.mp3") in the same directory.

3. Run the code

4. The code will open your webcam feed and start monitoring for drowsiness. When drowsiness is detected, an alert will be sent to the IBM Watson IoT platform, and the alarm sound will play.

## How it Works
The code uses OpenCV to capture video frames from your webcam.

It employs dlib to detect faces in the video frames.

For each detected face, it uses facial landmarks to locate the eyes.

The Eye Aspect Ratio (EAR) is calculated based on the positions of eye landmarks. When the EAR falls below a certain threshold, it indicates drowsiness.

If drowsiness is detected for a specified number of consecutive frames (EYE_AR_CONSEC_FRAMES), an alert is sent to the IBM Watson IoT platform.

An alarm sound is played to alert the individual when drowsiness is detected.

The code continuously updates the EAR and displays it on the video feed for monitoring.

## Configuration
You can adjust the EYE_AR_THRESH and EYE_AR_CONSEC_FRAMES constants to change the sensitivity of drowsiness detection.

Replace the alarm sound with your own MP3 file for a custom alarm.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
