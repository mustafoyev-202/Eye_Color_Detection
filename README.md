# Eye Color Detector 👁️ 🎨

An advanced computer vision application that detects and analyzes human eye color from images and video streams using
MTCNN (Multi-task Cascaded Convolutional Networks) and OpenCV. This tool can identify different eye colors and provide
detailed color composition analysis.

## ✨ Features

- Supports multiple eye color classifications (Blue, Blue Gray, Brown, Brown Gray, Brown Black, Green, Green Gray)
- Works with both images and video input (including webcam)
- Real-time face and eye detection using MTCNN
- Percentage breakdown of detected eye colors
- Visual output with annotations
- Support for multiple input sources (images, videos, webcam)

## 🚀 Getting Started

### Prerequisites

Install the required Python packages:

```bash
pip install numpy
pip install opencv-python
pip install mtcnn
pip install tensorflow  # Required for MTCNN
```

### Usage

Run the script with the following command-line arguments:

```bash
# For images
python eye_color_detector.py --input_path path/to/image.jpg --input_type image

# For video files
python eye_color_detector.py --input_path path/to/video.mp4 --input_type video

# For webcam (use webcam id, typically 0)
python eye_color_detector.py --input_path 0 --input_type video
```

## 🎯 Eye Color Classifications

The detector can identify the following eye colors:

- Blue
- Blue Gray
- Brown
- Brown Gray
- Brown Black
- Green
- Green Gray
- Other (unclassified)

## 🛠️ Technical Details

### Color Detection Algorithm

1. **Face Detection**:
    - Uses MTCNN for accurate face and facial landmark detection
    - Extracts eye coordinates and creates eye region masks

2. **Color Analysis**:
    - Converts image to HSV color space
    - Uses predefined HSV ranges for each eye color
    - Calculates color composition percentages
    - Determines dominant eye color

### HSV Color Ranges

```python
EyeColor = {
    "Blue": ((166, 21, 50), (240, 100, 85)),
    "Blue Gray": ((166, 2, 25), (300, 20, 75)),
    "Brown": ((2, 20, 20), (40, 100, 60)),
    # ... other color ranges
}
```

## 📊 Output

The program provides:

1. Visual output with:
    - Face boundary box
    - Eye region circles
    - Dominant eye color label
2. Console output with:
    - Dominant eye color
    - Percentage breakdown of all detected colors

## 💡 Key Features Explanation

### Face Detection

- Utilizes MTCNN for robust face detection
- Extracts facial landmarks for precise eye location
- Calculates eye distance for proper scaling

### Eye Region Processing

- Creates masks for isolated eye region analysis
- Adjusts eye region size based on face proportions
- Handles various face angles and positions

### Color Analysis

- Processes each pixel in the eye region
- Maps HSV values to predefined color categories
- Calculates color distribution statistics

## ⚙️ Customization

You can modify:

- HSV color ranges in `EyeColor` dictionary
- Eye region size calculation (`eye_radius`)
- Detection confidence thresholds
- Output visualization parameters

## 🔍 Troubleshooting

1. **No Face Detected**:
    - Ensure good lighting conditions
    - Check if face is clearly visible
    - Adjust image quality/resolution

2. **Incorrect Color Detection**:
    - Verify lighting conditions
    - Check for glare or reflections
    - May need to adjust HSV ranges

3. **Performance Issues**:
    - Reduce input image size
    - Check system resources
    - Consider GPU acceleration

## 📄 License

This project is open-source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Feel free to submit pull requests for:

- Additional eye color ranges
- Improved detection accuracy
- Performance optimizations
- New features

## 🙏 Acknowledgments

- MTCNN developers
- OpenCV community
- Contributors to HSV color classification research
