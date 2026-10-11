# Face Detection, Landmarks, Age/Gender & Expression

Real-time webcam face analysis in the browser using [face-api.js](https://github.com/justadudewhohacks/face-api.js).

## Features
- Face detection (Tiny Face Detector)
- 68-point facial landmarks
- Facial expression recognition
- Age and gender estimation
- Runs fully client-side, no backend

## Project Structure
├── index.html # page + video element
├── script.js # model loading, webcam, detection loop
├── style.css # overlay canvas styling
├── face-api.min.js # face-api.js library
└── models/ # pretrained model weights

## Run
Models load via `/models`, so serve from a local server (opening `index.html` directly won't work).

```bash
npx http-server
# or
python -m http.server 8000
```

Open `http://localhost:8000` and allow camera access.

## How It Works
1. Loads models: tinyFaceDetector, faceLandmark68Net, faceRecognitionNet, faceExpressionNet, ageGenderNet
2. Starts webcam stream
3. Every 100 ms: detect faces → landmarks → expressions → age/gender
4. Draws boxes, landmarks, expression scores and an "N year old gender" label on a canvas overlay

## Requirements
- Modern browser with webcam
- Serve from the same folder as `models/` (root path `/models`)

## Credits
- [face-api.js](https://github.com/justadudewhohacks/face-api.js) by Vincent Mühler
