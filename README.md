# Computer Vision Web Application

A Flask-based web application that implements multiple computer vision features including object detection, pose estimation, and PPE detection using YOLOv8.

## Project Structure

```
YoLo/
├── flaskopenCV.py        # Main Flask application for object detection
├── pose.py              # Pose estimation implementation
├── models/
│   ├── best.pt         # Custom trained PPE detection model
│   ├── yolov8n-pose.pt # YOLOv8 pose estimation model
│   └── yolov8n.pt      # YOLOv8 base model
├── templates/
│   ├── index.html      # Main webpage template
│   └── stop.html       # Stop camera page template
├── static/
│   └── styles/
│       └── index.css   # Styling for web interface
└── dataset/            # Training dataset directory
    ├── ppe_data.yaml   # Dataset configuration
    ├── train/          # Training data
    ├── valid/          # Validation data
    └── test/           # Test data
```

## Features

### Object Detection (flaskopenCV.py)
- Real-time PPE detection using custom trained YOLOv8 model
- Web interface for camera control
- Live video stream processing

### Pose Estimation (pose.py)
- Human pose detection and tracking
- Skeletal point mapping
- Real-time pose analysis

## Requirements

```
opencv-python>=4.7.0
flask>=2.0.0
ultralytics>=8.0.0
numpy>=1.24.0
```

## Installation

```bash
# Clone the repository
git clone (https://github.com/LeGiT300/YoLoCV/)

# Navigate to project directory
cd YoLo

# Install required packages
pip install -r requirements.txt
```

## Usage

### Running Object Detection

```bash
python flaskopenCV.py
```
Access the web interface at: `http://localhost:2000`

### Running Pose Estimation

```bash
python pose.py
```

## API Endpoints

### Object Detection endpoints
- `GET /` - Main page
- `POST /start` - Start camera feed
- `POST /stop` - Stop camera feed
- `GET /video_capture` - Stream video feed

## Model Information

- **PPE Detection Model (best.pt)**
  - Custom trained for detecting safety equipment
  - Classes: helmet, vest, etc.

- **Pose Estimation Model (yolov8n-pose.pt)**
  - Pre-trained YOLOv8 pose estimation model
  - Detects 17 key points on human body

## Development

To modify or extend the application:

1. Object Detection modifications:
   - Edit `flaskopenCV.py` for detection logic
   - Update templates in `templates/` for UI changes

2. Pose Estimation modifications:
   - Edit `pose.py` for pose detection features
   - Adjust model parameters as needed

## Error Handling

- Automatic camera resource cleanup
- Exception handling for video stream issues
- Graceful shutdown of web server

## Contributing

1. Fork the repository
2. Create a feature branch
3. Submit a pull request
