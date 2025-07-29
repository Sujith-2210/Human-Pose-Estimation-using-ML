# Advanced Human Pose Estimation

A real-time human pose estimation application built with Streamlit and MediaPipe that can analyze poses in images, videos, and live webcam feeds.

## Features

- **Multiple Input Sources**: Supports images, videos, and live webcam feed
- **Real-time Processing**: Fast pose detection and analysis
- **Angle Calculation**: Automatically calculates and displays elbow angles
- **Interactive Interface**: Easy-to-use web interface built with Streamlit
- **Adjustable Confidence**: Customizable confidence threshold for pose detection
- **Visual Feedback**: Displays pose landmarks and connections with colored annotations

## Demo

The application provides four main modes:
- **About App**: Information and instructions
- **Run on Image**: Upload and analyze static images
- **Run on Video**: Process video files frame by frame
- **Run on Webcam**: Real-time pose estimation using your camera

## Prerequisites

- Python 3.7 or higher
- Webcam (for live pose estimation)
- Compatible image formats: JPG, JPEG, PNG
- Compatible video formats: MP4, MOV, AVI

## Installation

1. **Clone or download the application files**

2. **Install required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application:**
   ```bash
   streamlit run app.py
   ```

## Dependencies

- `streamlit` - Web app framework
- `opencv-python` - Computer vision library
- `mediapipe` - Google's ML framework for pose estimation
- `numpy` - Numerical computing
- `pillow` - Image processing

## Usage

### Starting the Application

1. Open your terminal/command prompt
2. Navigate to the application directory
3. Run: `streamlit run app.py`
4. Your web browser will automatically open to the application

### Using Different Modes

#### Image Analysis
1. Select "Run on Image" from the sidebar
2. Adjust the confidence threshold (0.0 - 1.0)
3. Upload an image using the file uploader
4. View the processed image with pose landmarks and angle measurements

#### Video Analysis
1. Select "Run on Video" from the sidebar
2. Adjust the confidence threshold
3. Upload a video file
4. The application will process the video frame by frame

#### Webcam Analysis
1. Select "Run on Webcam" from the sidebar
2. Adjust the confidence threshold
3. Check "Run on Webcam" to start live processing
4. Uncheck to stop the webcam feed

### Understanding the Output

- **Pose Landmarks**: Colored dots and lines showing detected body joints
- **Angle Measurements**: Text overlay showing left and right elbow angles
- **Color Coding**: 
  - Orange/Red lines for pose connections
  - Pink/Purple dots for joint positions

## Technical Details

### Pose Detection
- Uses MediaPipe Pose solution for accurate human pose estimation
- Detects 33 key body landmarks including shoulders, elbows, wrists, hips, knees, etc.
- Calculates joint angles using vector mathematics

### Angle Calculation
The application specifically calculates elbow angles using the shoulder-elbow-wrist joint positions:
- Left elbow angle: Angle between left shoulder, elbow, and wrist
- Right elbow angle: Angle between right shoulder, elbow, and wrist

### Performance Optimization
- Real-time processing optimized for smooth video playback
- Adjustable confidence thresholds to balance accuracy and performance
- Efficient frame processing to minimize latency

## Troubleshooting

### Common Issues

**Application won't start:**
- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Check Python version (3.7+ required)

**Webcam not working:**
- Verify camera permissions in your browser/system
- Check if another application is using the camera
- Try restarting the application

**No pose detected:**
- Ensure the person is clearly visible in the frame
- Lower the confidence threshold
- Improve lighting conditions
- Make sure the full body or at least torso is visible

**Slow performance:**
- Close other applications to free up system resources
- Lower the confidence threshold
- Ensure good lighting for better detection accuracy

## Customization

### Adding New Angle Calculations
To calculate additional joint angles, modify the `process_image()` function:

1. Extract the required landmark coordinates
2. Use the `calculate_angle()` function with three points
3. Add text overlay to display the new angle

### Modifying Pose Visualization
- Adjust colors in the `DrawingSpec` parameters
- Change line thickness and circle radius
- Modify text font and size in `cv2.putText()`

## System Requirements

- **Minimum**: 4GB RAM, dual-core processor, integrated webcam
- **Recommended**: 8GB RAM, quad-core processor, dedicated webcam
- **Operating System**: Windows 10+, macOS 10.14+, or Linux (Ubuntu 18.04+)

## Author

**Created by Tenali Sujith Kumar**

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## Support

If you encounter any issues or have questions, please check the troubleshooting section above or open an issue in the project repository.
