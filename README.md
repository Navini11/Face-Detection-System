# Face Detection System 😊

This project demonstrates a real-time face detection system using OpenCV's deep learning module (DNN) with a Caffe model. The system captures video from a camera, processes each frame to detect faces, and displays the results in a window.

## 📋 Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## 🛠️ Installation

1. Clone the repository:

```sh
git clone https://github.com/Navini11/face-detection-system.git
cd face-detection-system
```

2. Install the required dependencies:

```sh
pip install -r requirements.txt
```

3. Download the necessary assets:

```sh
python download_assets.py
```

## 🚀 Usage

Run the face detection script:

```sh
python face_detection.py [camera_index]
```

- `camera_index` (optional): Index of the camera to use. Default is 0.

Example:

```sh
python face_detection.py 0
```

## 📦 Dependencies

- Python 3.x
- OpenCV
- Numpy

To install the dependencies, run:

```sh
pip install opencv-python-headless numpy
```

## 🗂️ Project Structure

- `face_detection.py`: Main script for face detection.
- `download_assets.py`: Script to download and unzip the required assets.
- `deploy.prototxt`: Model architecture file.
- `res10_300x300_ssd_iter_140000_fp16.caffemodel`: Pre-trained model weights.
- `requirements.txt`: List of required Python packages.

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or suggestions.

## 📜 License

This project is licensed under the MIT License.
```

## Requirements File (`requirements.txt`)

```plaintext
opencv-python-headless
numpy
```

## Download Assets Script (`download_assets.py`)

```python
import os
from zipfile import ZipFile
from urllib.request import urlretrieve

def download_and_unzip(url, save_path):
    print(f"Downloading and extracting assets....", end="")

    # Downloading zip file using urllib package.
    urlretrieve(url, save_path)

    try:
        # Extracting zip file using the zipfile package.
        with ZipFile(save_path) as z:
            # Extract ZIP file contents in the same directory.
            z.extractall(os.path.split(save_path)[0])

        print("Done")

    except Exception as e:
        print("\nInvalid file.", e)

URL = r"https://www.dropbox.com/s/efitgt363ada95a/opencv_bootcamp_assets_12.zip?dl=1"
asset_zip_path = os.path.join(os.getcwd(), f"opencv_bootcamp_assets_12.zip")

# Download if asset ZIP does not exist.
if not os.path.exists(asset_zip_path):
    download_and_unzip(URL, asset_zip_path)
