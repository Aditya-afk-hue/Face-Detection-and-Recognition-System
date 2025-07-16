# Face Detection and Recognition System 🚀

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5%2B-orange)
![Keras](https://img.shields.io/badge/Keras-2.6%2B-red)
![License](https://img.shields.io/badge/License-MIT-green)

A complete pipeline for real-time face detection and recognition using OpenCV and Keras. Capture facial data, preprocess images, and recognize individuals with machine learning.

## ✨ Key Features
- **Real-time Detection**: Live face detection from IP/webcam streams
- **Data Collection**: Automated capture and storage of facial images
- **Face Recognition**: Pre-trained Keras model for identification
- **Modular Design**: Separate components for collection, processing, and recognition
- **Easy Configuration**: INI files for customizable settings

## 📦 Installation

### Requirements
- Python 3.8+
- OpenCV 4.5+ (`opencv-python`)
- Keras 2.6+
- NumPy
- urllib3
- matplotlib (for visualization)

### Setup
```bash
# Clone repository
git clone https://github.com/yourusername/face-detection.git
cd face-detection

# Install dependencies
pip install -r requirements.txt  # Create this file with the above packages

# Download model files
wget https://github.com/opencv/opencv/raw/master/data/haarcascades/haarcascade_frontalface_default.xml
```

## 🛠️ Project Structure
```
.
├── config/                 # Configuration files
│   ├── codestyle.ini       # Code formatting rules
│   ├── encoding.ini        # Text encoding settings
│   ├── vcs.ini             # Version control settings
│   └── workspace.ini       # Project workspace config
├── src/                    # Main source code
│   ├── collect_data.py     # Data collection script
│   ├── consolidated_data.py # Data preprocessing
│   └── recognize.py        # Recognition script
├── models/                 # Store model files here
│   └── haarcascade_frontalface_default.xml
├── images/                 # Collected face images
├── clean_data/             # Processed data files
└── README.md               # This documentation
```

## 🚀 Usage Guide

### 1. Data Collection
```bash
python src/collect_data.py
```
- Captures 100 facial images from camera stream
- Saves to `images/[name]_[index].jpg` format
- **Customize**: Change IP camera URL in script (line 7)

### 2. Data Processing
```bash
python src/consolidated_data.py
```
- Processes raw images:
  - Converts to grayscale
  - Resizes to 100×100 pixels
  - Equalizes histograms
- Outputs:
  - `clean_data/images.p`: Pickled image array
  - `clean_data/labels.p`: Corresponding labels

### 3. Face Recognition
```bash
python src/recognize.py
```
- Real-time recognition from video stream
- Displays:
  - Face bounding boxes
  - Recognition confidence
  - Identity label
- Press 'q' to quit

## ⚙️ Configuration
Edit these files in `config/`:

| File | Purpose | Key Settings |
|------|---------|--------------|
| `codestyle.ini` | Code formatting | Indentation, line length |
| `workspace.ini` | Project settings | Recent files, save behavior |
| `vcs.ini` | Version control | VCS integration toggle |

## 🔧 Customization

### For New Users
1. Replace `192.0.0.4:8080` with your camera URL or `0` for webcam
2. Update label names in `recognize.py` (line 13)

### For Developers
```python
# To retrain model:
model = Sequential([
    Conv2D(32, (3,3), activation='relu', input_shape=(100,100,1)),
    # ... add your layers
])
model.compile(optimizer='adam', loss='categorical_crossentropy')
model.fit(train_images, train_labels, epochs=10)
```

## 🤝 Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.

## 📧 Contact
Your Name - your.email@example.com  
Project Link: [https://github.com/yourusername/face-detection](https://github.com/yourusername/face-detection)
```

