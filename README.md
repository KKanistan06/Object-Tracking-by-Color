# Object Tracking by Color

## Introduction
This project demonstrates **Object Tracking by Color** using **OpenCV** in Python. The system tracks objects in real-time based on their color in a video stream or pre-recorded video. It allows users to dynamically calibrate the HSV color range for accurate tracking.

The project contains two main components:
1. **colorCalibrationforHSV.py** – A tool for calibrating HSV values.
2. **object_tracking.py** – The script for real-time object tracking based on color.

## Features
- Real-time object tracking using OpenCV.
- Dynamic HSV color range calibration for accurate object detection.
- Tracks multiple objects of the same color.
- Flexible tracking for objects in video streams or files.

## Prerequisites

Before running the project, ensure you have the necessary dependencies.

### Requirements
- **Python 3.x**
- **OpenCV** (`cv2`)
- **Numpy**

You can install them via pip:

```bash
pip install opencv-python numpy
```

## Setup

### 1. Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/color-object-tracking.git
```

### 2. Calibrate HSV Range

First, run the **colorCalibrationforHSV.py** script to dynamically adjust the HSV range for the color you want to track:

```bash
python colorCalibrationforHSV.py
```

This will open a window with trackbars that let you adjust the HSV values until the color of interest is isolated in the video feed. Once you find the right range, note the values and update the **object_tracking.py** script.

### 3. Set Color Range

After determining the color range, open the **object_tracking.py** file and update the HSV color values:

```python
# Example for blue color:
lower_blue = np.array([100, 150, 0])
upper_blue = np.array([140, 255, 255])
```

### 4. Run the Object Tracker

After calibrating the color range, run the **object_tracking.py** script to start tracking objects based on the specified color.

- **For real-time webcam tracking:**
  ```bash
  python object_tracking.py
  ```

- **For tracking objects in a video file:**
  ```bash
  python object_tracking.py --video yourvideofile.mp4
  ```

## Project Structure

```
├── colorCalibrationforHSV.py  # HSV calibration tool
├── object_tracking.py         # Main script for color-based object tracking
├── examples/                  # Directory for example videos
├── README.md                  # Project documentation
└── requirements.txt           # List of project dependencies
```

## Customization

- **HSV Color Calibration:** Use `colorCalibrationforHSV.py` to fine-tune the color range for accurate object detection.
- **Tracking Multiple Objects:** The script tracks all objects within the specified color range. You can modify it to focus on specific object sizes or add shape filters (e.g., track only circular objects).
- **Resolution and Frame Rate:** For smoother tracking, you can lower the resolution of the video feed in `object_tracking.py`.

## Example

Here’s a demo of the color-based object tracking:

![Object Tracking Demo](link-to-demo-gif-or-screenshot)

## Troubleshooting

1. **Tracking Failure:**
   - Ensure proper lighting conditions.
   - Calibrate the HSV range carefully using the `colorCalibrationforHSV.py` tool.
   
2. **Multiple Objects:**
   - If there are multiple objects of the same color, all will be tracked. Adjust the detection logic if you want to track only one.

3. **Performance Issues:**
   - Lower the video resolution or use a more powerful machine for better performance.

## Future Enhancements
- Add support for tracking multiple colors simultaneously.
- Integrate shape recognition (e.g., only track circular objects).
- Implement a more advanced tracking algorithm (e.g., Kalman filter).

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
